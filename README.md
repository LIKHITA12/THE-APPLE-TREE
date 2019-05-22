#include<iostream.h>
#include<stdio.h>
#include<graphics.h>
#include<stdlib.h>
#include<string.h>
#include<conio.h>
#include<dos.h>

#define KeyLeft  75
#define KeyRight 77
#define KeyEsc   27
void far *buf1,*buf2,*buf3,*buf4,*buf5,*b1,*b2,*b3,*b4,*b5,*b6,*b7,*b8,*b9,*b10;
long size,s1,s2,s3,s4,s5,s6,s7,s8,s9;
int ad=76,i=0, p=169,q=415,l=76,ch,a=54,b=154,c=64,d=154 ,e=129,m=0,score=0,
lives=3,level=1;
int ms=0,ss=0,mm=0,k=25,sp;

class RESULT
{ int min,sec,mil,liv,lev,scor;
  char name[20];
  public:
 RESULT()
  { min=0;
    sec=0;
    mil=0;liv=3;lev=1;
    scor=0;
    strcpy(name,"aaa");
  }
void enter()
 { min=mm;
   sec=ss;
   mil=ms;
   liv=lives;
   scor=score;
   lev=level;
 }
void display()
 { puts(name); }
void entname()
 { gets(name); }
int retmin()
  {return min;}
int retsec()
  {return sec;}
int retmil()
  {return mil;}
int retliv()
  {return liv;}
int retlev()
  {return lev;}
int retscor()
  {return scor;}
char* retname()
  {return name;}

}r;

void tree()
 {
  //draw a tree
   int x,y;

   setcolor(2);
   setfillstyle(SOLID_FILL,GREEN);
   arc(142.7,29.7,180,260,13);
   arc(150,53,130,270,16);
   arc(156,69,160,290,8);
   arc(166,85,140,280,14);
   arc(180,105,130,285,13);
   arc(187,122,130,300,5);
   arc(202,130,150,320,12);
   arc(227,139,160,326,17);
   arc(252,152,170,330,13);
   arc(269,156,180,355,8);
   arc(286,161,180,325,11);
   line(130,29,527,29);
   ellipse(284,280,45,75,13,146);
   ellipse(368,280,105,130,13,146);
   arc(366,161,210,0,11);
   arc(384,158,190,0,8);
   arc(402,154,215,5,13);
   arc(427,144,225,5,17);
   arc(451,138,230,24,12);
   arc(465,129,240,50,5);
   arc(474,116,255,40,13);
   arc(493,98,240,40,14);
   arc(504,81,250,20,8);
   arc(511,66,270,55,16);
   arc(524,41,250,70,13);
   arc(290,132,190,20,7);
   arc(300,127,180,20,5);
   arc(315,128,160,0,10);
   arc(335,129,180,338,10);
   arc(350,132,160,0,5);
   arc(362,132,160,340,7);
   floodfill(300,50,2);
     setcolor(6);
     setfillstyle(SOLID_FILL,6);
      ellipse(285,280,260,75,13,149);
      ellipse(295,268,35,80,37,140);
      ellipse(355,268,100,145,37,140);
      ellipse(367,280,105,280,13,149);
      line(369,426,369,440);
      line(369,440,285,440);
      line(282,426,285,440);
      arc(290,132,190,20,7);
      arc(300,127,180,20,5);
      arc(350,132,160,0,5);
      arc(362,132,160,340,7);
      floodfill(350,240,6);




//to draw grass
 for(int j=0;j<350;j=j+56)
   { setcolor(2);
     ellipse(130+j,422,260,70,4,12);
     ellipse(130+j,425,340,78,10,15);
     ellipse(154+j,426,100,190,14,25);
     ellipse(155+j,426,100,205,9,25);
     ellipse(142+j,421,290,20,14,15);
     ellipse(147+j,427,340,70,16,13);
     ellipse(178+j,426,90,190,15,20);
     ellipse(180+j,426,100,215,10,20);
     ellipse(168+j,428,290,20,14,10);
     ellipse(169+j,432,340,60,17,10);
   }

  int k=390;
  setcolor(2);
  setfillstyle(SOLID_FILL,10);
  ellipse(130+k,422,260,70,4,12);
  ellipse(130+k,425,340,78,10,15);
  ellipse(154+k,426,110,190,14,25);
  ellipse(155+k,421,124,230,9,23);
  line(539,436,539,459);
  line(129,434,129,459);
  line(129,459,539,459);
  floodfill(300,445,2);
  setcolor(6);
  line(128,45,540,45);

  //basket
  //1
  size = imagesize(p-34+7,q-15,p+33+7,q+30);
  buf1 = malloc(size);
  getimage(p-34+7,q-15,p+33+7,q+30,buf1);

  //2
  s1 = imagesize(p-34+7+76,q-15,p+33+7+76,q+30);
  buf2 = malloc(s1);
  getimage(p-34+7+76,q-15,p+33+7+76,q+30,buf2);

  //3
  s2 = imagesize(p-34+7+152,q-15,p+33+7+152,q+30);
  buf3 = malloc(s2);
  getimage(p-34+7+152,q-15,p+33+7+152,q+30,buf3);

  //4
  s3 = imagesize(p-34+7+228,q-15,p+33+7+228,q+30);
  buf4 = malloc(s3);
  getimage(p-34+7+228,q-15,p+33+7+228,q+30,buf4);

  //5
  s4 = imagesize(p-34+7+304,q-15,p+33+7+304,q+30);
  buf5 = malloc(s4);
  getimage(p-34+7+304,q-15,p+33+7+304,q+30,buf5);

 }
void geti()
{//apple
 s5 = imagesize(153, 54, 167, 70);
	b1 = malloc(s5);
	b2 = malloc(s5);
	getimage(153, 54,167, 70, b1);

 s6 = imagesize(243,154, 257,170);
	b3 = malloc(s6);
	b4 = malloc(s6);
	getimage(243,154,257,170, b3);

 s7 = imagesize(316, 64, 330, 80);
	b5 = malloc(s7);
	b6 = malloc(s7);
	getimage(316, 64,330, 80, b5);

 s8 = imagesize(388,154, 402,170);
	b7 = malloc(s8);
	b8 = malloc(s8);
	getimage(388, 154,402,170, b7);

 s9 = imagesize(463,129, 477,145);
	b9 = malloc(s9);
	b10  = malloc(s9);
	getimage(463,129,477,145, b9);
}

void onea(int a,int sp)
 { getimage(153, a, 153+ 14, a + 16, b2);
   putimage(153, a, b1, COPY_PUT);
   delay(100);
   if((a >= 54) && (a < 410))
      { putimage(153, a, b2, COPY_PUT);
	delay(sp);
      }
 }

void twoa(int b,int sp)
 { getimage(243, b, 243+ 14, b+ 16, b4);
   putimage(243, b, b3, COPY_PUT);
   delay(100);
   if(b >154 && b < 410)
     { putimage(243, b, b4, COPY_PUT);
       delay(sp);
     }
  }

void threa(int c,int sp)
 { getimage(316, c, 316+ 14, c + 16, b6);
   putimage(316, c, b5, COPY_PUT);
   delay(100);
   if(c > 64 && c < 410)
     { putimage(316, c, b6, COPY_PUT);
       delay(sp);
     }
 }

void foura(int d,int sp)
 { getimage(388, d, 388+ 14, d + 16, b8);
   putimage(388, d, b7, COPY_PUT);
   delay(100);
   if(d > 154 && d < 410)
     { putimage(388, d, b8, COPY_PUT);
       delay(sp);
     }
 }

void fivea(int e,int sp)
 { getimage(463, e, 463+ 14, e + 16, b10);
   putimage(463, e, b9, COPY_PUT);
   delay(100);
   if(e >129 && e < 410)
    { putimage(463, e, b10, COPY_PUT);
      delay(sp);
    }

 }


void apple()

 { //draw an apple
   int a=60,b=30;
   setcolor(15);
   setfillstyle(SOLID_FILL,RED);

   //1
   bar(153,54,167,70);
   //2
   bar(453,54,467,70);
   //3
   bar(363+25,154,377+25,170);
   //4
   bar(213,84,227,100);
   //5
   bar(353,94,367,110);

   setfillstyle(SOLID_FILL,YELLOW);
   //6
   bar(253-10,154,267-10,170);
   //7
   bar(283+33,64,297+33,80);
   //8
   bar(413+10,94+10,427+10,110+10);
   //9
   bar(493-30,94+35,507-30,110+35);

   //8
   line(421+10,90+10,421+10,95+10);
   ellipse(436+10,100+10,65,170,15,13);
   ellipse(431+10,83+10,230,343,13,13);

   //9
   line(501-30,90+35,501-30,95+35);
   ellipse(516-30,100+35,65,170,15,13);
   ellipse(511-30,83+35,230,343,13,13);

   //1
   line(161,50,161,55);
   ellipse(176,60,65,170,15,13);
   ellipse(171,43,230,343,13,13);

   //6
   line(261-10,150,261-10,155);
   ellipse(276-10,160,65,170,15,13);
   ellipse(271-10,143,230,343,13,13);

   //7
   line(291+33,60,291+33,65);
   ellipse(306+33,70,65,170,15,13);
   ellipse(301+33,53,230,343,13,13);

   //2
   line(461,50,461,55);
   ellipse(476,60,65,170,15,13);
   ellipse(471,43,230,343,13,13);

   //3
   line(371+25,150,371+25,155);
   ellipse(386+25,160,65,170,15,13);
   ellipse(381+25,143,230,343,13,13);

   //5
   line(361,90,361,95);
   ellipse(376,100,65,170,15,13);
   ellipse(371,83,230,343,13,13);

   //4
   line(161+a,50+b,161+a,55+b);
   ellipse(176+a,60+b,65,170,15,13);
   ellipse(171+a,43+b,230,343,13,13);


 }
void border()
 {//draw a border
  int left,top,right,bottom;
   cleardevice();
   left = getmaxx()/2-200;
   top = getmaxy()/2-220;
   right = getmaxx()/2+220;
   bottom = getmaxy()/2+220;

   setfillstyle(SOLID_FILL,LIGHTBLUE);
   for(int p=1;p<10;p++)
    {
      setcolor(8);
      rectangle(left+p,top+p,right+p,bottom+p);
    }
   floodfill(200,100,8);


 }
void introduce()
 {settextstyle(7,0,3);
 setcolor(5);
 outtextxy(180,178,"Enter your name");
 gotoxy(30,14);
 r.entname();
 outtextxy(180,230,"I N S T R U C T I O N S");
 setcolor(2);
 line(180,260,490,260);
 setcolor(14);
 line(180,262,490,262);
 settextstyle(2,0,5);
 setcolor(WHITE);
 outtextxy(150,270,"1. Move the snake using Arrow Keys -> ");
 outtextxy(150,290,"    LEFT, RIGHT");
 outtextxy(150,310,"2. You will get 5 points for catching an apple");
 outtextxy(150,330,"3. Don't let it go else you may lose one life ");
 setcolor(2);
 rectangle(140,445,510,400);
 setcolor(4);
 rectangle(141,446,509,399);
  settextstyle(1,0,4);
  setcolor(1);
  outtextxy(150,400,"Press any key to play");
  getch();
  }


void rbasket(int p,int q,int l=0)
 {
   setcolor(1);
   setfillstyle(6,1);

   arc(p+80+l,q,180,360,30);
   arc(p+80+l,q,180,360,29);
   for(i=0;i<7;++i)
    { ellipse(p+81+l,q-i,210,330,36,8);
    }
   floodfill(176+80+l,428,1);
 }

void lbasket(int p,int q,int a=0)
 {
   setcolor(1);
   setfillstyle(6,1);

   arc(p+80+a,q,180,360,30);
   arc(p+80+a,q,180,360,29);
   for(i=0;i<7;++i)
    { ellipse(p+81+a,q-i,210,330,36,8);
    }
   floodfill(176+80+a,428,1);
 }

float exscreen()
 { char ch;
   cleardevice();
   border();
   setcolor(3);
   settextstyle(1,0,4);
   outtextxy(150,150,"Do You Want To Exit?");
   setcolor(2);
   rectangle(150,220,250,270);
   rectangle(400,220,500,270);
   setcolor(4);
   for(i=0;i<3;i++)
    { rectangle(151+i,221+i,249-i,269-i);
      rectangle(401+i,221+i,499-i,269-i);
    }
   setcolor(1);
   settextstyle(4,0,4);
   outtextxy(172,226,"Y");
   setcolor(15);
   outtextxy(195,226,"es");

   setcolor(1);
   settextstyle(4,0,4);
   outtextxy(436,226,"N");
   setcolor(15);
   outtextxy(457,226,"o");
   ch=getch();
   return ch;
 }

void del_rbasket(int l,int p,int q)
{
  if(l==0)
  { putimage(p-34+7,q-15,buf1,COPY_PUT); }
  else if(l==76)
   { putimage(p-34+7+76,q-15,buf2,COPY_PUT); }
  else if(l==152)
   { putimage(p-34+7+152,q-15,buf3,COPY_PUT); }
  else if(l==228)
   { putimage(p-34+7+228,q-15,buf4,COPY_PUT); }

}
void del_lbasket(int a,int p,int q)
{  if(a==-76)
  { putimage(p-34+7+76,q-15,buf2,COPY_PUT); }
  else if(a==0)
  { putimage(p-34+7+152,q-15,buf3,COPY_PUT); }
  else if(a==76)
   { putimage(p-34+7+228,q-15,buf4,COPY_PUT); }
  else if(a==152)
   { putimage(p-34+7+304,q-15,buf5,COPY_PUT); }
  else if(a==228)
   { //timage(p-34+7+304,q-15,buf5,COPY_PUT);
   }
}
void toapple(int m,int a,int b,int c,int d,int e,int sp)
{if((m==0)&&(a<410))
  {onea(a,sp);}

 else if((m==1)&&(b<410))
  { twoa(b,sp);  }

 else if((m==2)&&(c<410))
  { threa(c,sp); }

 else if((m==3)&&(d<410))
  { foura(d,sp);}

 else if((m==4)&&(e<410))
  { fivea(e,sp);}

 else
  outtextxy(0,0," ");

}

void Score(int sc,int li)
  { gotoxy (10,1);
    cout<<"SCORE:"<<sc;

    gotoxy(20,1);
    cout<<"LIVES:"<<li;
    r.enter();
  }

void inc()
 { delay(2);
   ms++;
 }

void show()
 { inc();
   if(ms>7)
     { ms=0;
       ss++;
     }
   else if(ss>59)
     { ss=0;
       mm++;
     }
   gotoxy(30,1);
   cout<<"TIME: "<<mm<<":"<<ss<<":"<<ms;
   r.enter();
 }

float result()
 { char ch;
   cleardevice();
   border();
   setcolor(3);
   settextstyle(1,0,4);
   outtextxy(250,150,"RESULT");
   setcolor(1);
   settextstyle(4,0,4);
   outtextxy(172,225,"Name: ");
   outtextxy(172,250,"Time: ");
   outtextxy(172,375,"Score: ");
   outtextxy(172,300,"Level:");
   outtextxy(172,325,"Lives: ");
   setcolor(15);
   gotoxy(35,15);
   r.display();
   gotoxy(35,17);
   cout<<r.retmin()<<":"<<r.retsec()<<":"<<r.retmil();
   gotoxy(35,19);
   cout<<r.retscor();
   gotoxy(35,21);
   cout<<r.retlev();
   gotoxy(35,23);
   cout<<r.retliv();


   ch=getch();
   return ch;
 }

float Level()
 {char j;
  if((mm==0)&&(ss==30)&&(ms==2))
		 {  gotoxy(45,1);
		    level=2;
		    cout<<"LEVEL:"<<level;  //level=2
		    k=12;
		  }

   else if((mm==1)&&(ss==11)&&(ms==2))
		 {  gotoxy(45,1);
		    level=3;
		    cout<<"LEVEL:"<<level;  //level=3
		    k=1;
		  }

   else if((mm==1)&&(ss==35)&&(ms==2))
		 {  gotoxy(45,1);
		    level=4;
		    cout<<"YOU WIN !!"<<level;  //level=end
		    r.enter();
		    sleep(3);
		    clearviewport();
		    to:
		    j=result();
		    if(j==KeyEsc)
		      { exit(0); }
		    else
		      { goto to;}
		  }
   r.enter();
   return k;
}

void main()
{ start:
    clrscr();
    randomize();
    char j;

    int gdriver = DETECT,gmode;
    initgraph(&gdriver,&gmode,"C:\\TC\\BGI");

      border();
      introduce();
      cleardevice();
      border();
      tree();
      apple();
      geti();
      lbasket(p,q,76);
      gotoxy(45,1);
      cout<<"LEVEL:"<<level;     //level=1

    again:
	a = 54;
	b = 154;
	c = 64;
	d = 154;
	e = 129;
	m = random(5);

	 while(m<5)
	  { if(lives==0)
	      { result();
		sleep(2);
		goto end; }
	    toapple(m,a,b,c,d,e,sp);
	     { if(m==0)
		{ a+=10;
		  if(a > 400)
		    { m++;
		      a += 10;
		      if ( l == -ad)
			 { score+=5;
			 }
		      else
			 { lives--;
			 }
		    }
		}
		else if(m==1)
		{  b+=10;
		   if(b > 400)
		      { m++;
			b += 10;
			if ( l == 0*ad )
			   { score+=5;
			   }
			else
			   { lives--;
			   }
		      }
		}
		      else if(m==2)
		{ c+=10;
		  if(c > 400)
		    { m++;
		      c += 10;
		      if ( l==ad )
			 { score+=5;
			 }
		      else
			 { lives--;
			 }
		    }
		}
		else if(m==3)
		{ d+=10;
		  if(d > 400)
		       { m++;
			 d += 10;
			 if ( l == 2 *ad )
			    { score+=5;;
			    }
			 else
			   { lives--;
			   }
			}
		 }
		 else if(m==4)
		 { e+=10;
		    if(e > 400)
			  { m++;
			    e += 10;
			    if ( l ==  3 *ad )
			       { score+=5;
			       }
			    else
			       { lives--;
			       }
			   }
		 }

			Score(score, lives);

	}

      show();
      sp=Level();

      if(kbhit())
       {ch=getch();
       switch(ch)
	{ case KeyLeft: { if(l<=-70)
			   {break;}
			  else
			   {   l-=76;
			    lbasket(p,q,l);
			     del_lbasket(l,p,q);
			     del_rbasket(l,p,q);

			     break;
			   }
			}

	  case KeyRight:{ if(l>=220)
			   {break;}
			  else
			   {   l+=76;
			     rbasket(p,q,l);
			     del_rbasket(l,p,q);
			     del_lbasket(l,p,q);

			     break;
			   }
			}

	  case KeyEsc: { goto lab;
		       }
		 default: break;
	 }
    }
 }

if(m>4)
   { goto again;}

lab:
  { r.enter();
    j=exscreen();
    if((j=='y')||(j=='Y'))
       { goto end;}
    else if((j=='n')||(j=='N'))
       { goto start;    }
    else
      { goto lab;}
  }
end:
   closegraph();

 }
