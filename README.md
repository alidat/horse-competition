# horse-competition
A work in progress! - An application that calculates and displays the scores and positions of riders in a horse jumping competition. 

//****************************************************************************
// Alida Thomas        HorseJumping.java
//
// This application calculates the riders score during a jumping competition
// and displays the group the other players have scored in as well as the 
// score and placement of the rider so far. 
//****************************************************************************

public class HorseJumping {

    public static void main(String[] args) {
    
        // Create variables that determine score. 
        // Set scores for hypothetical rider. 
        boolean completedCourse = true;
        int judgeScore = 700;
        int jumpsSuccessful = 4;
        int timeBonus = 150;
        
        // Create scores and positions of other riders.
        int scorePosition = calculateScorePosition(1500);
        displayScorePosition("Meghan", scorePosition);
        
        scorePosition = calculateScorePosition(900);
        displayScorePosition("Alex", scorePosition);
        
        scorePosition = calculateScorePosition(400);
        displayScorePosition("Jesse", scorePosition);
        
        scorePosition = calculateScorePosition(50);
        displayScorePosition("Jacob", scorePosition);
        
        scorePosition = calculateScorePosition(1000);
        displayScorePosition("Zoe", scorePosition); 
        
        // Display results for new rider.
        int yourScore = calculateScore(completedCourse, judgeScore, jumpsSuccessful, timeBonus);
        System.out.println("Your final score is: " + yourScore + ". You are in group " + scorePosition + " in the competition");
    }
        // Display scores and positions of other riders.
         public static void displayScorePosition( String riderName, int scorePosition){
            System.out.println(riderName + " is currently group "
            + scorePosition + " in the competition.");
    }

        // Method that determines rider position based on score. 
         public static int calculateScorePosition(int riderScore){
             int position = 4;
             
             if(riderScore >= 1000) {
                 position = 1;
        }   else if(riderScore >= 500){
                 position = 2;  
        }   else if(riderScore >= 100){
                 position = 3;
        }
            return position;
        }

        // Method that calculates final score of new rider. 
        public static int calculateScore(boolean completedCourse, int judgeScore, int jumpsSuccessful, int timeBonus){
    
            if(completedCourse){
               int finalScore = judgeScore + jumpsSuccessful + timeBonus;
               return finalScore;
       }
           return -1;
       }
       }
