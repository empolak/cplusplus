// CSC 234
// Name:
// Date:
// Assignment #5 

// Instructions: Please input this program into the online compiler 
// https://www.onlinegdb.com/online_c++_compiler#
// Send me your completed file and the output in the console (you can 
// copy and paste)

// This lab will extend the previous labs and build off the instructions 
// from class. This lab we are going to build off of polymorphism 
// There will be 1 base class for gradeItem with a virtual function and 2 bases classes: lab and quiz. 
// The derived classes will implement getPoints() differently based on whether it is a lab or quiz
    
// ACTION: Take the base class structure in the separate file and add it into this code
// ACTION: create objects for a lab and a quiz
// ACTION: print the results

#include <iostream>
#include <cstring>
#include <string>

using namespace std;

class student {
 char name[80]; // private by default
 public:
  	void putname(char *n); // these are public
  	char getname();
 private:
  	double grade; // private
    public:
  	void putgrade(double w); // back to public
  	double getgrade();
};

void student::putname(char *n)
{
  	strcpy(name, n);
}

char  student::getname()
{
  	return *name;
}

void student::putgrade(double w)
{
    	grade = w; 
}

double student::getgrade()
{
  return grade;
}

class school
{
	char sname[8] = "FRCC", location[10] = "Longmont" ;

   public:
	//create a method to getName() and return sname
	char getSchoolName()
	{
	    return *sname;
	}
	
	//create a method to getLocation() and return location
	char getLocation()
	{
	    return *location;
	}
};

class csc : public student, public school
{
    char semester[20], name[20], instructor[20]; 
        
  public:        
    // create a method that sets the instructor
    void putclassName(char *n)
    {
        //add code here
        strcpy (name, n);
    }
    
    // create a method that sets the instructor
    void putInstructor(char *n)
    {
        //add code here
        strcpy (instructor, n);
    }
    
    // create a method that sets the semester (e.g. spring)
    void putSemester(char *n)
    {
        //add code here
        strcpy (semester, n);
    }
    
    // create a method to return intrusctor
    char getInstructor ()
    {
        // code to return instructor
        return *instructor;
    }
        
    // create a method to return semester
    char getSemester  ()
    {
        // code to return semester
        return *semester;
    }
        
    // create a method to return semester
    char getName  ()
    {
        // code to return semester
        return *name;
    }

};


// ACTION: Insert code for new classes here
// Base class for grade items
// Has a virtual function for getPoints (how many points go into gradebook)
class gradeItem
{
    public:
        int grade ;  //internal grade variable
        gradeItem(){grade = 0;}
        // constructor to pass in numeric grade
        gradeItem (int g)  
        {
            grade = g;
        }
        
        virtual float getPoints(){return grade;}

};

// Derived class for lab grades. They are worth 25% of total grade 
class lab : public gradeItem
{
    public:
        float getPoints()
        {
            return grade *.25;
        }
        lab(int g) : gradeItem(g)
        {

        }
};

// Derived class for quiz grades. They are worth 10% of total grade
class quiz : public gradeItem
{
    public:
        float getPoints()
        {
            return grade *.1;
        }
        quiz(int g) : gradeItem(g)
        {

        }
};


// This is the main part of your program
int main() 
{ 
  // let's get rid of ted and replace with s
  csc *c;
  
  lab *l = new lab(90);
  quiz *q = new quiz (100);

  double Total = l->getPoints();

  cout << "total lab points " << Total << "\n";
  cout << "total quiz points " << q->getPoints() << "\n";

  try {
    //ted = new student[20];
    c = new csc[20];
  } catch (bad_alloc xa) {
       cout << "Allocation Failure\n";
       return 1;
  }
  
  // initializing the students and their grades
  char name[3][80] = {"Grant","Loki", "Thor"};
  char instr[20] = "Grant Miller";
  int grade[3] = {100, 90, 85}; 

  // setting the variables in the objects
  for (int i =0; i<3; i++)
  {
    c[i].putname(name[i]);
  	c[i].putgrade(grade[i]);

    // NEW CODE add setting the classname of the class (csc234)
    c[i].putclassName ((char *)"csc234");

    // NEW CODE add setting the instructor name of the class (csc234)
    c[i].putInstructor (instr);
    
     // NEW CODE add setting the semester of the class (csc234)
    c[i].putSemester ((char *)"Spring 2021");
  }
 
  
  for (int i =0; i<3; i++)
  {
    cout << "Semester " <<  c[i].getSemester() << " and instructor " <<c[i].getInstructor() << "\n";
  	cout << c[i].getname() << " received a grade of ";
  	cout << c[i].getgrade() << " in class " << c[i].getSemester() << "\n";
  }
  
  delete c;
  
  return 0; 
}
