# pr1maks
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace PR1Makso
{
    class MPlate
    {
        private string name;

        public string Name
        {
            get { return name; }
            set 
            {
                name = value;
            }
        }

        public void ShowName()
        {
            Console.WriteLine("Motherboard name: " + name);
        }

        public MPlate(string _name)
        {
            if (_name.Length >= 20 && _name.Length <= 150)
            {
                name = _name;
            }

            else
            {
                name = "defaultplatename";
            }
        }
    }

    class PBlock
    {
        private string name;
        private int power;

        public string Name
        {
            get { return name; }
            set
            {
                name = value;
            }
        }

        public int Power
        {
            get { return power; }
            set
            {
                power = value;
            }
        }

        public void ShowName()
        {
            Console.WriteLine("Powerblock name: " + name + " " + power.ToString() + " W");
        }

        public PBlock(string _name, int _power)
        {
            name = _name;
            power = _power;
        }
    }

    class Processor
    {
        private string name;

        public string Name
        {
            get { return name; }
            set
            {
                name = value;
            }
        }

        public void ShowName()
        {
            Console.WriteLine("Processor name: " + name);
        }

        public Processor(string _name)
        {
            name = _name;
        }
    }

    class Videocard
    {
        private string name;
        private int amount;

        public string Name
        {
            get { return name; }
            set
            {
                name = value;
            }
        }

        public int Amount
        {
            get { return amount; }
            set
            {
                if(value > 512)
                {
                    amount = 512;
                }

                else if(value < 2)
                {
                    amount = 2;
                }

                else
                {
                    amount = value;
                }
            }
        }
        public void ShowName()
        {
            Console.WriteLine("Videocard name: " + name + " " + amount.ToString() + " Gb");
        }

        public Videocard(string _name, int _amount)
        {
            name = _name;
            amount = _amount;
        }
    }

    internal class Program
    {
        static void Main(string[] args)
        {
            string mplate;
            string pblock;
            string processor;
            string videocard;
            int power;
            int amount;

            Console.WriteLine("Write motherboard name");
            mplate = Console.ReadLine();

            Console.WriteLine("Write powerblock name");
            pblock = Console.ReadLine();
            Console.WriteLine("Write powerblock power");
            power = Convert.ToInt32(Console.ReadLine());

            Console.WriteLine("Write processor name");
            processor = Console.ReadLine();

            Console.WriteLine("Write videocard name");
            videocard = Console.ReadLine();
            Console.WriteLine("Write videocard memory amount");
            amount = Convert.ToInt32(Console.ReadLine());

            MPlate plate1 = new MPlate(mplate);
            PBlock block1 = new PBlock(pblock,power);
            Processor proc1 = new Processor(processor);
            Videocard vid1 = new Videocard(videocard,amount);

            plate1.ShowName();
            block1.ShowName();
            proc1.ShowName();
            vid1.ShowName();
            Console.ReadLine();
        }
    }
}
