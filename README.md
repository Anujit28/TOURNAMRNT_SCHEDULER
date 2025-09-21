Round Robin Tournament Scheduler in Python. Generates match schedules for any number of teams, ensuring each team gets rest between matches. Supports custom or auto-generated team names. Perfect for planning sports leagues, esports tournaments, or friendly competitions.

# **Round Robin Tournament Scheduler with Rest Days
* Automatically generates a round robin schedule for any number of teams.
* Calculates total number of matches.

## **How It Works**

Uses the circle method for round robin scheduling:

1. One team is fixed, the others are rotated each round.
2. Matches are organized into rounds to guarantee rest.

## **Example Output**

```
Round 1:
  Team 1 vs Team 4
  Team 2 vs Team 3

Round 2:
  Team 1 vs Team 3
  Team 4 vs Team 2

Round 3:
  Team 1 vs Team 2
  Team 3 vs Team 4

Total Matches: 6
```

## Future Enhancements

Divide teams into groups and schedule within each group.
Automatically assign match dates and times.
Export schedule to CSV or Excel.
Support knockout rounds after group stage.
