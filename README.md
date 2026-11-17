# Travel Planner

This planner helps travellers build an itinerary, compare destinations, estimate a budget, or revise part of a trip.

## Files and use

`system-prompt.md` contains the complete system instructions. Copy it into **System instructions** in Google AI Studio Playground, then start a fresh conversation. GitHub stores the prompt; it does not run the planner or automatically update Playground.

## Menu

1. **Plan an itinerary** — create a day-by-day trip.
2. **Choose between destinations** — compare options and refine a recommendation together.
3. **Check a budget** — estimate trip costs.
4. **Revise a plan** — change part of an existing itinerary.

A general request displays the menu. Select a number, an activity name, or make a clear request in your own words. You can switch activities at any point; relevant details carry forward within the conversation.

## New activity

Choose between destinations uses guided information collection from Lecture 9. Give two or three destinations and your main priority. The planner asks for missing details, compares the options, and waits for a concern or preference. It uses your reply to refine its recommendation and asks whether you want to choose or adjust it. The activity ends when you accept a destination, stop, or switch activities. An itinerary is offered only as a next step.

## Existing features

The Assignment 2 features remain: day-by-day itineraries, a trip brief separating confirmed details from assumptions, budget estimates with totals and remaining funds, targeted revisions, clarification of ambiguous destinations, and travel-only boundaries. A confirmed destination and duration are required for an itinerary, but not for an initial comparison. Budget scope must be clear before monetary estimates.

## Version history

The unchanged Assignment 2 prompt was saved on `main` in commit `1b7c415` with the message **Preserve Assignment 2 starting prompt**. The menu and destination activity were developed on `conversational-features` in commit `d78e791`.

## Tests

Two fresh Google AI Studio Playground conversations used the complete prompt from commit `d78e791`, Gemini 3.8 Flash, Medium thinking, Google Search grounding enabled, and the same default advanced settings (maximum output 65536 tokens, no stop sequence).

- Test 1: A general request displayed the four-option menu. Selecting `2` started destination comparison. After comparing Lisbon and Valencia for food and culture, the planner provisionally recommended Lisbon. A request to avoid steep hills changed the recommendation to Valencia. It waited for confirmation, then confirmed Valencia and offered an itinerary without generating one.

- Test 2: An activity-name request started a Montreal/Quebec City comparison with 3 days, 2 travellers, museums, and no car. Before answering the refinement question, the traveller asked for a Montreal itinerary in their own words. The planner acknowledged the switch and retained those details in its trip brief. After a request to proceed with a general plan, it produced a 3-day car-free museum itinerary.

No routing or continuity revision was needed after these two tests. Screenshots and observations are included in the assignment submission.

## Limits

The planner gives suggestions, not bookings or purchases. Prices and availability require reliable current sources; estimates are not confirmed prices. These conversation tests check routing and continuity, not every possible input or the accuracy of all travel advice.
