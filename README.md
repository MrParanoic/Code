# Code
my first code, when i started 
static void Main(string[] args)
        {
            bool isWork = true;
            string[] fullName = {
             "Корчагин Давид Александрович",
             "Осипов Матвей Львович",
             "Борисов Михаил Платонович",
             "Быкова Анна Марковна",
             "Трофимов Тимофей Романович",
             "Сорокина Алиса Дмитриевна",
             "Верещагин Степан Иванович",
             "Соколова Елизавета Захаровна",
             "Морозов Глеб Алексеевич",
             "Митрофанова Василиса Марковна"};
            string[] workSkill = {
                "Военный консультант",
                "Издатель",
                "Виноградарь",
                "Монтажник связи",
                "Монтажник",
                "Вирусолог",
                "Подводник",
                "Инженер-гальваник",
                "Диакон",
                "Нарколог"};
            //Описать функцию заполнения массивов – досье, функцию форматированного вывода, функцию поиска по фамилии и функцию удаления досье.
            //Функция расширяет уже имеющийся массив на 1 и дописывает туда новое значение.
            while (isWork)
            {
                Console.WriteLine("Добавить досье");
                Console.WriteLine("Вывести все досье");
                Console.WriteLine("Удалить досье");
                Console.WriteLine("Поиск по фамилии");
                Console.WriteLine("Выход");
                string choiceMenu = Console.ReadLine();
                Console.Clear();
                if (choiceMenu == "1")
                {
                    choice(ref fullName,ref workSkill);
                }
                if (choiceMenu == "2")
                {
                    drawMenu(fullName,  workSkill);
                }
                if (choiceMenu == "3")
                {
                    deletDogs(fullName,workSkill);
                }
                if (choiceMenu == "4")
                {
                    searchPeaple(fullName, workSkill);
                }
                if (choiceMenu == "5")
                {
                    exitFromProgg(isWork);
                }
            }
        }
        static void choice(ref string[] NameList, ref string[] SkillsLisd)
        {
            Array.Resize(ref NameList, NameList.Length + 1);
            Array.Resize(ref SkillsLisd, SkillsLisd.Length + 1);
            Console.WriteLine("Введите полное имя ");
            string fullNameOfNewSpecialist = Console.ReadLine();
            Console.WriteLine("Введите специальность");
            string workSkillsOfNewSpecialist = Console.ReadLine();
            NameList[^1] = fullNameOfNewSpecialist;
            SkillsLisd[^1] = workSkillsOfNewSpecialist;
            Console.ForegroundColor = ConsoleColor.Yellow;
            Console.WriteLine("Вы успешно добавили досье");
            Console.ResetColor();
            Console.WriteLine("Нажмите Enter, что бы вернуться в меню");
            Console.ReadLine();
            Console.Clear();
        }
        static void drawMenu(string[] NameList, string[] SkillsLisd)
        {
            for (int i = 0; i < NameList.Length && i < SkillsLisd.Length; i++)
            {
                Console.WriteLine("(" + (i + 1) + ")" + NameList[i] + "-" + SkillsLisd[i]);
            }
            Console.WriteLine("Нажмите Enter, что бы вернуться в меню");
            Console.ReadLine();
            Console.Clear();
        }
        static void deletDogs(string[] NameList, string[] SkillsLisd) 
        {
            Console.WriteLine("Введите нумерацию досье которую хотите удалить ");
            int deletDocsOfWorkers = Convert.ToInt32(Console.ReadLine());
            if (deletDocsOfWorkers > NameList.Length)
            {
                Console.WriteLine("Такого досье не существует");
                Console.WriteLine("Нажмите Enter, что бы вернуться в меню");
                Console.ReadLine();
                Console.Clear();
            }
            for (int i = 0; i < NameList.Length && i < SkillsLisd.Length; i++)
            {
                if (deletDocsOfWorkers == i + 1)
                {
                    NameList[i] = " ";
                    SkillsLisd[i] = " ";
                }
            }
        }
        static void searchPeaple(string[] NameList, string[] SkillsLisd) 
        {
            Console.WriteLine("Поиск по фамилии");
            string search = Console.ReadLine();
            for (int i = 0; i < NameList.Length; i++)
            {
                if (NameList[i].Contains(search))
                {
                    Console.WriteLine("Досье с этой фамилией находится под номером" + "(" + (i + 1) + ")");
                    break;
                }
            }
            Console.WriteLine("Нажмите Enter, что бы вернуться в меню");
            Console.ReadLine();
            Console.Clear();
        }
        static void exitFromProgg(bool Exit) 
        {
            Exit = false;
            Console.WriteLine("Заходите еще");
        }
