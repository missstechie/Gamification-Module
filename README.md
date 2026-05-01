
# Gamification Engine for Health Workers (MVP)

## Overview
This project simulates a basic gamification system designed to motivate and engage field-level health workers. It incorporates core gamification mechanics such as points, streaks, and badges, directly aligned with common healthcare workflows like patient visits, vaccinations, and registrations.

## Features
- **Points System**: Workers earn points for completing specific actions.
- **Streak System**: Rewards consistent daily engagement.
- **Badge System**: Recognizes achievements based on accumulated points.
- **Modular Design**: Easy to extend and integrate with existing systems.

## Getting Started

### Prerequisites
- Python 3.x
- Jupyter Notebook or Google Colab environment

### Installation
No specific installation is required beyond a Python environment. The code runs directly in a Jupyter or Colab notebook.

### Usage

1.  **Define Workers and Actions**: Customize the `workers` and `actions` dictionaries to suit your specific needs.

    ```python
    workers = {
       "Anjali": {"points": 0, "streak": 0}
    }

    actions = {
       "visit": 10,
       "vaccination": 20,
       "registration": 15
    }
    ```

2.  **Perform Actions**: Use the `perform_action` function to award points.

    ```python
    perform_action("Anjali", "visit")
    perform_action("Anjali", "vaccination")
    ```

3.  **Update Streak**: Call `update_streak` to maintain or reset a worker's streak.

    ```python
    update_streak("Anjali", worked_today=True)
    ```

4.  **Get Badge**: Determine a worker's current badge based on their points.

    ```python
    badge = get_badge(workers["Anjali"]["points"])
    print(f"Anjali's Badge: {badge}")
    ```

### Example Workflow

```python
# Simulate actions for Anjali
perform_action("Anjali", "visit")
perform_action("Anjali", "vaccination")
update_streak("Anjali", worked_today=True)

# Display Anjali's current status
print("Worker: Anjali")
print("Points:", workers["Anjali"]["points"])
print("Streak:", workers["Anjali"]["streak"])
print("Badge:", get_badge(workers["Anjali"]["points"]))
```

## Design Considerations
-   **Offline-First**: Designed with the understanding that field workers may operate in areas with limited connectivity. Logic can be executed locally and synced later.
-   **Background Sync**: Can be integrated with background job mechanisms (e.g., Android WorkManager, iOS Background Tasks) for seamless data synchronization.
-   **Modular Logic**: The functions are modular, allowing for easy integration into existing mobile applications or backend systems.

## Future Work
-   **Leaderboard System**: Implement a global or team-based leaderboard to foster healthy competition.
-   **Challenge-Based Rewards**: Introduce specific challenges with unique rewards (e.g., "Complete 5 vaccinations in a day to earn a bonus badge").
-   **Real User Activity Data Integration**: Connect with actual user activity logs to automate point and streak updates.
-   **Time-Based Streaks**: Enhance the streak system to account for missed days with a grace period.
-   **Dynamic Action Values**: Allow for configurable or dynamically changing point values for actions.

