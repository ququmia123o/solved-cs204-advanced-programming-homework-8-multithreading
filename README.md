Download Link: https://assignmentchef.com/product/solved-cs204-advanced-programming-homework-8-multithreading
<br>
<h1>Introduction</h1>

<strong> </strong>In this homework, you are going to practice multithreading by simulating a Relay Race. A relay race is a track and field event in which athletes run a pre-set distance carrying a baton before passing it onto the next runner. In the homework, first, runners of the teams will wait for a start signal to start the race together. Then the threads will start and when a runner in the team reaches to destination, the next runner will start. After the last runner in the team reaches to destination, the rank of the team will be updated. Finally, when all teams finish the race, the scoreboard will be printed.




In the homework, you have a struct for <strong>Runners</strong> as follows:

struct Runner { public:

// VARIABLES // DEFINITIONS       float speed; // Runner’s speed    int rid;      // Runner’s ID

int tid;      // Runner’s team ID

bool reached; // Whether runner has reached destination

thread* t; // Runner’s thread handle




// Constructor

Runner(int rid, int tid):speed(random(4, 8)), rid(rid),tid(tid),reached(false){    //TODO: Start the corresponding thread here in the constructor

// Printing information about it         print.lock();               cout &lt;&lt; “*******
Team id: ” &lt;&lt; tid &lt;&lt; “tRunner id: ” &lt;&lt; rid &lt;&lt; “
Speed:

” &lt;&lt; speed &lt;&lt; “
*******
”;

print.unlock();

}

};

There is also another struct which is for <strong>Teams: </strong>

<strong> </strong>

struct Team { public:

vector&lt;Runner&gt; teamList;  bool finished;     int rank;     int count;

int currentRacer;




Team(int count):count(count), currentRacer(0), finished(false) {}

};

You are also given <strong>main</strong> function, <strong>start </strong>function that threads will run and a helper function,<strong> random,</strong> for assigning random speed values to runners. You don’t need to make any change in the main function, however you are free to edit any part of the given code as long as it works as it should be.




The parts you need to implement is commented with <strong>TODO</strong> notes. The parts you are responsible for:

<ul>

 <li>Start the corresponding thread in the constructor of <strong>Runner</strong></li>

 <li>Update the runner’s travelled distance in the <strong>start</strong> function</li>

 <li>Implement the mechanism to start the next thread (next runner in the team) in the <strong>start</strong> function</li>

 <li>implement a function to print the rankings</li>

</ul>




<h1>Output</h1>

The output for the given main function should be as follows (<strong>Don’t forget the ranking may be different since we are working on threads, don’t expect them to be exactly the same</strong>):

*******

Team id: 0      Runner id: 0

Speed: 4.005

*******

*******

Team id: 1      Runner id: 0

Speed: 6.25434

*******

*******

Team id: 2      Runner id: 0

Speed: 4.77322

*******

*******

Team id: 3      Runner id: 0

Speed: 7.23496

*******




***************************************************************************** *

Race starting with the signal now

***************************************************************************** *

*******

Team id: 3      Runner id: 1

Speed: 5.65618

*******

*******

Team id: 1      Runner id: 1

Speed: 7.78698

*******

*******

Team id: 2      Runner id: 1

Speed: 6.78121

*******

*******

Team id: 0      Runner id: 1

Speed: 6.70345

*******

*******

Team id: 1      Runner id: 2

Speed: 5.71648

*******

*******

Team id: 3      Runner id: 2

Speed: 5.98675

*******

*******

Team id: 2      Runner id: 2

Speed: 6.71468

*******

*******

Team id: 0      Runner id: 2

Speed: 4.25098

*******

Team 1 has finished the race

Team 3 has finished the race

Team 2 has finished the race

Team 0 has finished the race







—- RANKS —-




<ul>

 <li>– Team 1</li>

 <li>– Team 3</li>

 <li>– Team 2</li>

 <li>– Team 0</li>

</ul>

Press any key to continue . . .