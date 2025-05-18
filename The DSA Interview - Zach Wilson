## The DSA Interview

### What does this interview look like?
- It could be the code screen (initial round)
    - Usually easier questions, maybe 3-4 python questions (45-60 minutes)

- If it's onsite round, expect more diffuct and involv questions, usually 60 minutes

Quick Tips 
- Slow down! Every second in this interview counts and wating time coding something you don't understand will destroy your chances!

- Remember being pushed for optimization means your on the right track!

- You might get lucky and see a question you've already done!

- Don't overdo it with Leetcode prep, also don't go in rusty!
    - Focus on the medium

- Use Python!!
    - for faster programming
- Remember Big O notation
    - O(1) >> O(log n) >> O(n) >> O(nlogn) >> O(n^2) >> O(n!) >> O(n^n)
- Trading off a little space to save a little time is usually the right answer!
- 90% of data engineering interviews are solved with stacks, queues, maps, lists and trees
- Use sets instead of lists when checking membership of something!
    - checking a membership of a set is O(1)
    - checking a membership of a list is O(n), a lot slower
- Experience pain for more memory retention

### What matters in the interview?
- Communicating your thought process
    - Leverage the interviewer for a little bit of nudge/help/hint

- Getting the right answer
- The speed in which you identify the right answer
- The quality of the code that you write
- Optimizing the answer and understanding the tradeoffs


### The Space-Time Tradeoff

- Remember  algrithms have both space complexity and time complexity!
    - Caching/Storing pre-computed values in a map will cost you space but save you time
- If you store n keys in a hashmap, the space complexity is O(n)

### Optimizations
- Are you using nested loops? O(n^2) never is a good enough solution
    - Maybe think about how to leverage more space here?
- Are you asked to do operations in place? (i.e. use O(1) space)
    - Think about pointers of the problem and how to not use any complex variables


## The SQL Interview
### The types of interviews you'll face

- The "screener" interview
- The "deep" interview

### The "screener" interview

- 45-60 minutes, 3-5 easy to medium SQL questions
    - This isn't to gauge your skills. This is just the light filter of "can this engineer even code?"
- the interviewer is allowed to give hints but no more than 1 or 2
- communicate and talk things through, the screener is a human

### Mistake engineers make
- Jumping right into code and not asking any clarifying questions
- Relying too heavily on engine specific UDFs
    - Not knowing what is and isn't ANSI-compliant
        - That funky array method you're trying to use probably isn't
        - Sticj with ANSI-only functions and methods
- Relying too heavily on window functions and not knowing how to replicate with regular JOINs
    - they just might want to see your thought process
- Not talking at all/being too anxious and talking too fast


### The language -> SQL keyword mapping
- Ordinal words (first,second,third,etc.)
    - RANK, DENSE_RANK, ROW_NUMBER
        - if you need 1 row per ordinal - use ROW_NUMBER
        - if you can have ties in ordinals - use DENSE_RANK
        - RANK is mostly not used
- Rolling 7/28/30/365 day sum, average, etc
    - SUM(√alue) OVER (PARTITION BY dim ORDER BY date ROWS BETWEEN 30 PRECEEDING AND CURRENT ROW)
- "Metric by Dimension"
    - This either means PARTITION BY or GROUP BY depending on how that metric is generated
- Hierarchy, Funnels, month-over-month, year-over-year
    - Use a self-join or a window function
        - Interviewers often will push you to use self-join as a further optimization
        - Strong signal to be able to solve a problem the other away.
    - "Find all the things that don't have X attribute"
        - LEFT JOIN + WHERE

### Other things that matter
- Query readability matters
    - Don't do nasty subqueries
- Your though process matters
- Solving enough question also matters
    - a little sense of urgency

### The "deep" SQL interview
- Usually 1 hour to 90 minutes
    - Really drilled on things like:
        - Table scans
            - Predicate pushdowns
        - Indices/Partitioning
        - Optimizations
        - Query plans
- YOur though  process matters more than getting a perfect answer
- be personable and likable
    - The inverviews grade you on a 4 scale
        - 1 Strong pass, not getting the job
        - 2 weak pass, not getting the job
        - 3 weak accept
        - 4 strong accept
        - should be mostly 4s, with one or two threes
    - treat the interviewer/s like a human
    - How likeable you are could mean the difference between 2 and 3 if you were really on the edge on some of the problems
- Ask for your interviews to not be back-to-back the whole day so your brain can refresh and recharge for at least 30 minutes between interviews
- I always exercise for 30+ minutes before any "onsite" technical interview to reduce anxiety and jitters

## The Behavioral Interview

### What does this interview look like?
- A 60ish minute interview talking about situations and past projects
    - Recruiter, HR, or Engineering Manager

### How to succeed in this interview
- Radiate positivity and passion
- Show willingness to learn
- UNDERSTAND THE COMPANY CULTURE
    - do not emanate a brilliant jerk vibes

### How to talk about past projects
- You should have a sense of joy and enthusiasm when talking about the stuff you've built in the past
    -   communicate the impact
- Building software around your interest will help

### Workplace dynamics
- Truthfully talk about hard situations you've been in!
- It's even better if you can honestly talk about hard situations and show how you resolve them!
    - i.e. balancing priorities
        - communicate with stakeholder
        - dive in depth where the interviewer wants to go
- Have a baked example for:
    - when you handled constructive feedback
    - when you overcame a challenge
    - your accomplished that you're most proud of
- its all about building trust

