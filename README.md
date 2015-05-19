# Repository-12
Create class DateAndTime that combines the modified Time2 class of Exercise 8.7 and the modified Date class of Exercise 8.8. Modify method incrementHour to call method nextDay if the time is incremented into the next day. Modify methods toString and toUniversalString to output the date in addition to the time. Write a program to test the new class DateAndTime. Specifically, test incrementing the time to the next day.

public class Date 
{
	private int day;
	private int month;
	private int year;
	private String Month;
	private int daysOfYear;
	private int daysInMonth;
	//private int MonthDays[] = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
	public Date(int month, int day, int year)
	{
		this.day=day;
		this.month=month;
		this.year=year;
	}
	public Date(String Month,int day,int year)
	{
		this.Month=Month;
		this.day=day;
		this.year=year;
	}
	public Date(int daysOfYear,int year)
	{
		this.daysOfYear=daysOfYear;
		this.year=year;
	}
	public void setmonth(int M)
	{
		month=M;
	}
	public int getmonth()
	{
		return month;
	}
	public void setday(int D)
	{
		day=D;
	}
	public int getday()
	{
		return day;
	}
	public void setyear(int Y)
	{
		year=Y;
	}
	public int getyear()
	{
		return year;
	}
	/*public void setdaysInMonth(int daysInMonth)
	{
		this.daysInMonth=daysInMonth;
	}
	public int getdaysInMonth()
	{
		return daysInMonth;
	}*/
	/*public void daysOfYear(int daysOfYear)
	{
		this.daysOfYear=daysOfYear;
	}
	public int getdaysOfYear()
	{
		return daysOfYear;
	}*/
	public String toString()
	{
		return String.format(this.getmonth()+"/"+this.getday()+"/"+this.getyear());
	}
	public void setMonth(String m)
	{
		Month=m;
	}
	public String getMonth()
	{
		return Month;
	}
	publi c String toString1(int i)
	{	
	
		String months[]={"January","Feb","March", "April", "May", "June", "July", "August", "September", "October",
								"Novemeber", "December"};
		return String.format(months[i-1]+" "+this.getday()+","+this.getyear());
	}
	public String toString2()
    {
        int j;
        int MonthDays[] = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
        int daysOfYear[]=new int[365];
        for(j=0;j<MonthDays.length;j++)
        {
            daysOfYear[j]=j+1;
        }
        return String.format(MonthDays[daysOfYear[j+1]]+","+this.getyear());
    }
	
}
// Test Program

import java.util.Scanner;


public class DateTest
{
	public static void main (String args[])
	{
		int j=0;
		Scanner input=new Scanner(System.in);
		System. out.print("Enter Day: ");
		int Day=input.nextInt();
		System. out.print("Enter Month: ");
		int Month=input.nextInt();
		System. out.print("Enter Year: ");
		int Year=input.nextInt();
		System.out.println("Display of Date is as follows");
		Date date=new Date( Month, Day, Year);
		System.out.println("Date displayed in MM/DD/YYYY: "+date);
		System.out.println("Date displayed in MM/DD/YYYY: "+date.toString1(Month));
		System.out.printf("Date displayed in DDD/YYYY:"+date.toString2());
	}
}
