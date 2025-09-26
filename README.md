# Kickstarter-Contributions-Patterns

## 1. Data Handling Summary
To prepare the dataset for analysis, the following steps were applied:
- Remove duplicates → to ensure accuracy and avoid double counting.
- Handle missing values in pledged → replaced nulls with 0 (assuming null means no funding received).
- Remove rows with missing reward_levels → since reward tiers are essential for contribution analysis.

- Fix category/subcategory text formatting issues:
  
      A. Replaced Film& amp; Video → Film & Video.

      B. Replaced Filmdamp; Video → Film & Video.

      C. Replaced Country& amp; fol → Country & Folk.

- New engineered columns:

      - min_reward and max_reward: extracted from reward_levels.

      - avg_contribution_per_backer: calculated as pledged / backers.

      - CleanedGoal: for successful projects replace goals  with pledged only when goal is less than 0.8 of the pledged amount 

      - funded_percentage: calculated as (pledged ÷ cleangoal) × 100.


These steps ensured clean, consistent, and reliable data for analyzing how backer contributions influence campaign outcomes.


## 2. Data Dictionary
  - project_id (Integer): Unique ID of each project.
    
  - name (Text): Title of the Kickstarter project.
    
  - url (Text): Project webpage link
    
  - category (Text): Main project category (e.g., Games, Film & Video).
    
  - subcategory (Text): Subcategory of the project.
    
  - location (Text): Project’s location (City, State, Country).
    
  - status (Text): Campaign outcome (successful, failed, live, canceled, suspended).
    
  - goal (Decimal): Original funding goal set by the creator.
    
  - pledged (Decimal): Total amount pledged by backers.
    
  - funded_percentage (Decimal): Percentage of the goal achieved (pledged ÷ goal × 100).
    
  - backers (Integer): Number of backers who contributed.
    
  - funded_date (Date): Date the project ended funding.
    
  - levels (Integer): Number of reward tiers offered.
    
  - reward_levels (Text): List of reward tiers (e.g., $25, $100, $500).
    
  - min_reward (Decimal): Minimum pledge tier available.
    
  - max_reward (Decimal): Maximum pledge tier available.
    
  - updates (Integer): Number of updates posted by the creator.
    
  - comments (Integer): Number of comments posted by backers.
    
  -  duration (Decimal): Length of the campaign in days.
    
  - CleanedGoal (Decimal): Adjusted goal (pledged used if goal < 0.8 × pledged and campaign successful).
    
  - project-success (Decimal): Percentage of the goal achieved (pledged ÷ cleangoal × 100)

## 3. Findings
- Backer Participation: Games, Design, and Technology attract the most backers.

- Contribution Size: Film & Video has the highest average contribution per backer.

- Reward Options: More reward tiers → higher pledges (especially in successful projects).

- Goal Size: Projects with goals under $50K achieve higher funded percentages.

- Engagement: Projects with more comments → larger pledged amounts.

## 4. Limitation
- No backer ID data, so repeat contributions (loyalty) cannot be tracked.


## 5. Conclusion 
Backer contribution patterns show that campaign outcomes depend on goal-setting, reward structures, and engagement.






















