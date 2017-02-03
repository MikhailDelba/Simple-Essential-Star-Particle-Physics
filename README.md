# Simple-Essential-Star-Particle-Physics
//Easy Essential Star Particle Physics

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Star
{
    class Star
    {

       public int x, y, vx, vy;

        public void move()
        {
            x += vx;
            y += vy;
            if (x > 80 || x <= 1)
            {
                vx = -vx;
            };
            if (y >= 25 || y <= 1)
            {
                vy = -vy;
            }
        }

        public void show()
        {
            Console.SetCursorPosition(x, y);
            Console.Write("*");
        }
        public Star()
        {
        }
        public Star(int _x, int _y, int _vx, int _vy)
        {
            x = _x;
            y = _y;
            vx = _vx;
            vy = _vy;
        }

    }

    class Program
    {
        static void Main(string[] args)
        {
            Star star, star2;
            star = new Star();
            star2 = new Star(10,10,1,1);
            star.x = 40;
            star.y = 10;
            star.vx = 1;
            star.vy = 1;
            do
            {
                star.move();
                star.show();
                star2.move();
                star2.show();
                System.Threading.Thread.Sleep(100);
                Console.Clear();
            }
            while (!Console.KeyAvailable);
            Console.ReadKey();
        }
    }
}
