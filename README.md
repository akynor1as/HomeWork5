# HomeWork5
static void Main(string[] args)
        {
            Console.WriteLine("Выберите одно из доступных заданий: ");
            Console.WriteLine("Задание 1.");
            

            int number = int.Parse(Console.ReadLine());
            Console.Clear();
            switch (number)
            {
                case 1:

                    Console.WriteLine("Задание 1. ");
                    Task1();
                    break;

                default:

                    Console.WriteLine("Введен некорректный номер задачи.");
                    break;
            }
        }
        

        static void Task1() // б) с использованием ругелярных выражний
        {
            Console.WriteLine("Введите логин с латинской буквы.");
            string login = Console.ReadLine();

            byte[] bytes = new byte[192];
            int kol = 0;
            for (int i = 0; i < 47; i++)
            {
                bytes[kol] = (byte)i;
                kol++;
            }
            for (int i = 58; i < 64; i++)
            {
                bytes[kol] = (byte)i;
                kol++;
            }
            for (int i = 91; i < 96; i++)
            {
                bytes[kol] = (byte)i;
                kol++;
            }
            for (int i = 123; i < 255; i++)
            {
                bytes[kol] = (byte)i;
                kol++;
            }

            char[] chars = System.Text.Encoding.ASCII.GetChars(bytes);

            bool flag = false;

            foreach (var item in chars)
            {
                for (int i = 0; i < login.Length; i++)
                {
                    if (login[i] == item)
                    {
                        flag = true;
                    }
                }
            }

            if (login.Length >= 2 && login.Length <= 10 && Char.IsDigit((char)login[0]) == false && flag == false)
                Console.WriteLine("Логин - {0}, подходит", login);
            else
                Console.WriteLine("Логин не подходит.");

        }
