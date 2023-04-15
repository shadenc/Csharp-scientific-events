        
        class Attendee 
        {
            private string name;
            private int age;
            private string specialization;
            private int id;

            public Attendee(String n, int a, string s, int i)
            {
                Name = n;
                Age = a;
                Specialization = s;
                Id = i;

            }

            public string Name
            {
                get { return name; }
                set
                {
                    if (value != null)
                        name = value;
                    else
                        throw new Exception("value can’t be null");
                }
            }

            public int Age
            {
                get { return age; }
                set
                {
                    if (value > 0)
                        age = value;
                    else
                        throw new Exception("number must be positive");
                }
            }

            public string Specialization
            {
                get { return specialization; }
                set
                {
         if (value == "web design" || value == "programming " || value == "artificial intelligence ")
                        specialization = value;
                    else
                        throw new Exception("incorrect entery of specialization");
                }
            }


          

              
           public int Id
            {
                get { return id; }
                set
                {
                    if (value > 0)
                        id = value;
                    else
                        throw new Exception("number must be positive");
                }
            }


            public override string ToString()
            {
        return string.Format("Name:{0}  age:{1} specialization:{2} id:{3}", Name, Age, Specialization, Id);
            }
             }



          
         abstract class ScientificEvent 
        {


            private string title;
            private string location;
            private int maxTicket;
            private int id;

            Attendee[] atds;
            int Aelement = 0;


            public ScientificEvent(string t, string l, int mt, int i)
            {
                Title = t;
                Location = l;
                MaxTicket = mt;
                Id = i;

                atds = new Attendee[MaxTicket];
            }


            public string Title
            {
                get { return title; }
                set
                {
                    if (value != null)
                        title = value;
                    else
                        throw new Exception("The value must be not null");
                }
            }


            public string Location
            {
                get { return location; }
                set
                {
                    if (value != null)
                        location = value;
                    else
                        throw new Exception("The value must be not null");
                }
            }


            public int MaxTicket
            {
                get { return maxTicket; }
                set
                {
                    if (value > 0)
                        maxTicket = value;
                    else
                        throw new Exception("The value must be > 0");
                }
            }


            public int Id
            {
                get { return id; }
                set
                {
                    if (value > 0)
                        id = value;
                    else
                        throw new Exception("The value must be > 0");
                }
            }


            public abstract bool acceptAttendee(Attendee a);


            public void addAttendee(Attendee a)
            {
                bool exist = false;
                if (Aelement < atds.Length)
                {

                    for (int i = 0; i < Aelement; i++)
                    {
                        if (a.Id == atds[i].Id)
                        {
                            exist = true;
                            break;
                        }

                    }
                    if (!exist && acceptAttendee(a))
                    {
                        atds[Aelement] = a;
                        Aelement++;
                        Console.WriteLine("Reservation successful");
                    }
                    else
                        Console.WriteLine("Sorry, there are a problem with the reservation process");

                }
                else
                    Console.WriteLine("Sorry, the event full..");
            }


            public bool removeAttendee(Attendee a)
            {
                bool exist = false;
                for (int i = 0; i < Aelement; i++)
                {
                    if (a.Id == atds[i].Id)
                    {
                        atds[i] = null;
                        exist = true;

                    }
                }
                return exist;
            

            public override string ToString()
            {
return "Title: " + Title + "Location: " + Location + "ID: " + Id + "Number of Attendances is: " + maxTicket;
            }
        }


         class Workshop : ScientificEvent 
        {


            private string track;
            private int nbWeeks;
            private string[] speakers;


      public Workshop(string title, string location, int maxTicket, int ID, string tr, int nw, string[] sp)
               : base(title, location, maxTicket, ID)
            {
                track = tr;
                nbWeeks = nw;
                speakers = sp;
            }
            public string Track
            {
                get { return track; }
                set
                {
               if (value == ("web design") || value == ("programming") || value == ("acritical inelegant"))
                        track = value;

                    else
                        throw new Exception("The track is not valid ");
                }
            }


            public int NbWeeks
            {
                get { return nbWeeks; }
                set
                {
                    if (value > 0)
                        nbWeeks = value;
                    else
                        throw new Exception("The value must be > 0");
                }
            }


            public override string ToString()
            {
                return " Track: " + Track + " Number of weeks:" + NbWeeks + "speakers ;" + speakers;
            }


            public override bool acceptAttendee(Attendee a)
            {

                if (a.Specialization == ("web design") || a.Specialization == ("programming") ||
               a.Specialization == ("acritical inelegant"))
                    return true;
                else
                    return false;

            }
 }
        4. Training Class

        class Training : ScientificEvent 
        {


            private string profName;



            public Training(string titile, string location, int maxTicket, int ID, string pn)
                : base(titile, location, maxTicket, ID)
            {
                ProfName = pn;
            }


            public override string ToString()
            {
                return " and Professor Name:" + profName;
            }


            public string ProfName
            {
                get { return profName; }

                set { profName = value; }
            }


            public override bool acceptAttendee(Attendee a)
            {
                if (a.Age > 12)
                    return true;
                else
                    return false;

           }
        }
    }
}

       // Main Method

      static void Main(string[] args) 
        {
            
                try
                {
     ScientificEvent[] EventsNum;

     Console.WriteLine("How many events do you want to insert?");

     int size = Convert.ToInt32(Console.ReadLine());
     EventsNum = new ScientificEvent[size];
     int eventCount = 0;
     int choice = 0;
    
                while (choice != 5)
     {
     Console.WriteLine("1. Add new workshop, and add all attendances" +
     "\n2. Add a new training to the array, and add all attendances" +
     "\n3. Print the sum of maximum number of attendances (maxTicket) in all the workshops" + "\n4. Print the information of all training events that have the same professor’s name." + "\n5. Exit");
     choice = Convert.ToInt32(Console.ReadLine());
    
                switch (choice)
     {
                case 1:
     Console.WriteLine("Enter the title, location, max number of ticket and the Id for the event:");

     string title = Console.ReadLine();
     string location = Console.ReadLine();
     int max = Convert.ToInt32(Console.ReadLine());
     int id = Convert.ToInt32(Console.ReadLine());

     Console.WriteLine("Enter the track, Number of weeks, and number of speakers in this workshop :");

     string track = Console.ReadLine();
     int NumWeek = Convert.ToInt32(Console.ReadLine());
     int NumSpeakers = Convert.ToInt32(Console.ReadLine());
     string[] speakers = new string[NumSpeakers];
     ScientificEvent MyworkshopEvent = new Workshop(title, location, max, id, track, NumWeek, speakers);

     Console.WriteLine("How many attendance in this workshop:");
                            
     int attendanceCount = Convert.ToInt32(Console.ReadLine());

                                if (attendanceCount < max)
                                {
                                    for (int i = 0; i < attendanceCount; i++)
                                    {
                                 Console.WriteLine("Enter the attendee name:");
                                 string name = Console.ReadLine();

                                 Console.WriteLine("Enter the attendee age:");
                                 int age = Convert.ToInt32(Console.ReadLine());

                                 Console.WriteLine("Enter the attendee specialization:"); 
                                 string specialization = Console.ReadLine();

                                 Console.WriteLine("Enter the attendee id:");
                                 int attendeeId = Convert.ToInt32(Console.ReadLine());

                         MyworkshopEvent.addAttendee(new Attendee(name, age, specialization, attendeeId));
                                    }
                                }
                                else
                                    Console.WriteLine("Number of attendance must be less than " + max);
                                if (eventCount < size)
                                {

                                    EventsNum[eventCount] = MyworkshopEvent;
                                    eventCount++;
                                }
                                else
                                    Console.WriteLine("The event List is full.");
                                break;

                 case 2:
     Console.WriteLine("Enter the title, location, max number of ticket and the Id for the event:");

     title = Console.ReadLine();
     location = Console.ReadLine();
     max = Convert.ToInt32(Console.ReadLine());
     id = Convert.ToInt32(Console.ReadLine());

     Console.WriteLine("Enter the professor name for this training:");
     string profName = Console.ReadLine();

     Training MytrainingEvent = new Training(title, location, max, id, profName);
     Console.WriteLine("How many attendance in this workshop:");
     attendanceCount = Convert.ToInt32(Console.ReadLine());

                                if (attendanceCount < max)
                                {
                                    for (int i = 0; i < attendanceCount; i++)
                                    {
                                 Console.WriteLine("Enter the attendee name:");
                                 string name = Console.ReadLine();

                                 Console.WriteLine("Enter the attendee age:");
                                 int age = Convert.ToInt32(Console.ReadLine());

                                 Console.WriteLine("Enter the attendee specialization:");
                                 string specialization = Console.ReadLine();

                                 Console.WriteLine("Enter the attendee id:");
                                 int attendeeId = Convert.ToInt32(Console.ReadLine());

                        MytrainingEvent.addAttendee(new Attendee(name, age, specialization, attendeeId));
                                    }
                                }
                                else
                                    Console.WriteLine("Number of attendance must be less than " + max);
                                if (eventCount < size)
                                {
                                    EventsNum[eventCount] = MytrainingEvent;
                                    eventCount++;
                                }
                                else
                                    Console.WriteLine("The event List is full.");
                                break;

                


 case 3:
     int sum = 0;
                                for (int i = 0; i < EventsNum.Length; i++)
                                {
                                    if (EventsNum[i] is Workshop)
                                        sum = sum + EventsNum[i].MaxTicket;
                                }
     Console.WriteLine("The sum of maximum number of attendances in all the workshops is: " + sum);
                                break;

                 case 4:

     Console.WriteLine("Enter the professor name:");
     profName = Console.ReadLine();

                                for (int i = 0; i < EventsNum.Length; i++)
                                {
                                    if (EventsNum[i] is Training)
                                    {
                                        Training t = (Training)EventsNum[i];
                                        if (t.ProfName.Equals(profName))
                                            Console.WriteLine(t);
                                    }
                                }
                                break;

                 case 5:

                                break;

                 default:
                                Console.WriteLine("Invalid Choice..");
                                break;
                        }
                    }
                    Console.ReadKey();


                }
                catch (Exception e)
                {
                    Console.WriteLine(e.Message);
                }
            }

        }















