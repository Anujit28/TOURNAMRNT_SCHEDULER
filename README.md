def round_robin_with_rest(teams):
    """
    Generates a round robin schedule with rest days (no back-to-back matches).
    Uses the circle method.
    """
    if len(teams) % 2 != 0:
        teams.append("BYE")  # Add dummy if odd number of teams
    
    n = len(teams)
    rounds = n - 1
    schedule = []

    for r in range(rounds):
        round_matches = []
        for i in range(n // 2):
            team1 = teams[i]
            team2 = teams[n - 1 - i]
            if team1 != "BYE" and team2 != "BYE":
                round_matches.append((team1, team2))
        schedule.append(round_matches)
        # Rotate teams (except the first one)
        teams = [teams[0]] + [teams[-1]] + teams[1:-1]
    
    return schedule


def main():
    print(" Round Robin Tournament Scheduler (With Rest) \n")
    
    # Input number of teams
    num_teams = int(input("Enter number of teams participating: "))
    
    # Input team names or auto-generate
    team_input = input("Do you want to enter team names? (yes/no): ").strip().lower()
    if team_input == "yes":
        teams = [input(f"Enter name of Team {i+1}: ") for i in range(num_teams)]
    else:
        teams = [f"Team {i+1}" for i in range(num_teams)]
    
    # Generate schedule
    schedule = round_robin_with_rest(teams)
    
    # Print schedule round by round
    for r, matches in enumerate(schedule, 1):
        print(f"\n Round {r}:")
        for match in matches:
            print(f"  {match[0]} vs {match[1]}")
    
    total_matches = sum(len(round_matches) for round_matches in schedule)
    print(f"\nTotal Matches: {total_matches}")


if __name__ == "__main__":
    main()
