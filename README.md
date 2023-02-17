# code
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp2
{
    internal class PhanSo
    {
        private int tuSo;
        private int mauSo;

        public int TuSo { get => tuSo; set => tuSo = value; }
        public int MauSo { get => mauSo; set => mauSo = value; }

        //ham contructor 
        public PhanSo() { mauSo = 0; tuSo = 1; }
        public PhanSo (int t=0 , int m = 1) { tuSo = t; mauSo = m;  }

        public void NhapPS()
        {
            Console.WriteLine("Nhap tu so: ");
            this.tuSo = int.Parse(Console.ReadLine());
            Console.WriteLine("Nhap mau so:");
            this.mauSo = int.Parse(Console.ReadLine());
        }
        public void XuatPS()
        {
            Console.WriteLine("{0}/{1}", tuSo , mauSo);
        }
        public PhanSo Cong(PhanSo ps)
        {
            PhanSo kq= new PhanSo();
            kq.tuSo = this.tuSo * ps.mauSo + this.mauSo * ps.tuSo;
            kq.mauSo = this.mauSo * ps.mauSo;
            return kq;
        }
        //xay dung ham cai dat phep toan
        public static PhanSo operator+(PhanSo ps1, PhanSo ps2)
        {
            int tu = ps1.tuSo * ps2.mauSo + ps1.mauSo * ps2 .tuSo;
            int mau = ps1.mauSo * ps2.mauSo;
            PhanSo kq = new PhanSo(tu, mau);
            return kq;
        }
        public static PhanSo operator -(PhanSo ps1, PhanSo ps2)
        {
            int tu = ps1.tuSo * ps2.mauSo - ps1.mauSo * ps2.tuSo;
            int mau = ps1.mauSo * ps2.mauSo;
            PhanSo kq = new PhanSo(tu, mau);
            return kq;
        }
        //xay dung chuc nang phuong thuc xuat
        public override string ToString()
        {
            string s;
            s = this.tuSo.ToString()+"/"+this.mauSo.ToString();
            return s;
        }
    }
}
