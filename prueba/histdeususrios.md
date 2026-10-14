# User Stories and Acceptance Criteria

Format: As a [actor], I want to [action], for [benefit]. Estimation in points (1-5) and planned sprint.

---

## Epic A: Accounts and Access

* **HU-01 Registration** (Sprint 2 - 3 pts - Assignee: Jessica)[cite: 12]  
  As a visitor, I want to create an account, so that I can use the application[cite: 12].  
  * Given an unregistered email and a password of at least 8 characters, the account is created and responds with 201[cite: 12].  
  * If the email already exists, it responds with 409 without revealing data from other accounts[cite: 12].  
  * The password is saved securely hashed; it never appears in responses or logs[cite: 12, 16].

* **HU-02 Login** (Sprint 2 - 3 pts - Assignee: Jessica)[cite: 13]  
  As a user, I want to log in, so that I can access my trips[cite: 13].  
  * With correct credentials, the session/token is created and responds with 200[cite: 13].  
  * With incorrect credentials, it responds with 401 using a generic message[cite: 13].  
  * Protected routes accessed without a session respond with 401[cite: 13].

---

## Epic B: Trips and Participants

* **HU-03 Create Trip** (Sprint 2 - 3 pts - Assignee: Danna)[cite: 13]  
  As a user, I want to create a trip with a destination, dates, and budget, so that I can organize my getaway[cite: 13].  
  * With valid data, the trip is created and the creator is assigned as the organizer[cite: 13].  
  * An end date prior to the start date or a negative budget responds with 400 with error details[cite: 13].

* **HU-04 View My Trips** (Sprint 2 - 2 pts - Assignee: Danna)[cite: 13]  
  As a participant, I want to view the list of my trips, so that I can quickly access each one[cite: 13].  
  * Only trips where I am a participant are listed[cite: 13].  
  * Attempting to open someone else's trip responds with 403[cite: 13].

* **HU-05 Add Participants** (Sprint 2 - 3 pts - Assignee: Jessica)[cite: 13]  
  As an organizer, I want to add friends and peers to the trip, so that they can collaborate[cite: 13].  
  * Only the organizer can add or remove members; another participant receives 403[cite: 13].  
  * Adding someone already included responds with 409[cite: 13].  
  * The added person sees the trip in their list[cite: 13].

* **HU-06 Edit or Delete Trip** (Sprint 3 - 2 pts - Assignee: Danna)[cite: 13]  
  As an organizer, I want to edit or delete the trip, so that I can correct changes in plans[cite: 13].  
  * Only the organizer can perform this action[cite: 13].  
  * Deleting requires confirmation and wipes all related data[cite: 13].

---

## Epic C: Itinerary

* **HU-07 Add Activities** (Sprint 3 - 3 pts - Assignee: Danna)[cite: 13]  
  As a participant, I want to register activities with a day, date, and time, so that everyone knows the plan[cite: 13].  
  * The date must fall within the trip's date range[cite: 13].  
  * Title is mandatory; time must use a valid format[cite: 13].

* **HU-08 View Sorted Itinerary** (Sprint 3 - 2 pts - Assignee: Danna)[cite: 13]  
  As a participant, I want to view activities grouped by day and sorted by time, so that I can follow the plan[cite: 13].  
  * Activities appear grouped by date and sorted chronologically[cite: 13].

* **HU-09 Edit and Delete Activities** (Sprint 3 - 2 pts - Assignee: Jessica)[cite: 13, 14]  
  As a participant, I want to modify or remove activities, so that I can adjust the itinerary[cite: 13, 14].  
  * Only trip participants can modify them; outsiders receive 403[cite: 13, 14].

---

## Epic D: Expenses and Balances

* **HU-10 Register Expense** (Sprint 3 - 5 pts - Assignee: Jessica)[cite: 14]  
  As a participant, I want to record an expense indicating who paid and who it is split among, so that accounts stay fair[cite: 14].  
  * Amount greater than 0, valid category, and at least one involved member[cite: 14].  
  * The sum of shares equals the total amount[cite: 14].  
  * Involved members must belong to the trip[cite: 14].

* **HU-11 View Balances** (Sprint 3 - 5 pts - Assignee: Jessica)[cite: 14]  
  As a participant, I want to see who owes whom, so that we can settle accounts at the end[cite: 14].  
  * Each person's balance equals what they paid minus what they owe[cite: 14].  
  * The sum of all balances is 0[cite: 14].  
  * Displays the minimum list of transfers[cite: 14].

* **HU-12 Register Settlement Payment** (Sprint 4 - 3 pts - Assignee: Danna)[cite: 14]  
  As a participant, I want to record that I have paid off a debt, so that the balance updates[cite: 14].  
  * After registering the payment, both persons' balances are adjusted[cite: 14].  
  * Payments greater than the debt or payments to oneself are not allowed[cite: 14].

---

## Epic E: Luggage and Budget

* **HU-13 Luggage Checklist** (Sprint 4 - 3 pts - Assignee: Danna)[cite: 14]  
  As a participant, I want an interactive checklist of items to bring, so that I don't forget anything[cite: 14].  
  * I can add, mark as ready, and delete items[cite: 14].  
  * State is preserved when reloading the page[cite: 14].

* **HU-14 Budget and Charts** (Sprint 4 - 5 pts - Assignees: Jessica & Danna)[cite: 14]  
  As a participant, I want to view charts comparing spent budget against available budget, so that I can control spending[cite: 14].  
  * Displays total spent, remaining balance, and breakdown by category[cite: 14].  
  * Charts update when adding or modifying an expense[cite: 14].  
  * If an expense exceeds the budget, a visual alert is shown[cite: 14].

---

### Definition of Done (DoD)
A user story is considered finished when: it meets its acceptance criteria, validates inputs on the server, has automated tests, passed review via pull request, is integrated into `develop`, and the issue is moved to "Done"[cite: 14].