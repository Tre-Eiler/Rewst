# Rewst.io Looping Workflow

## Overview
This Rewst.io workflow is designed to loop in the event of a failure due to issues such as outages. The workflow includes a built-in delay and a loop limit to prevent infinite looping.

## Inputs 
The workflow accepts the following five inputs (all fields are required):

1. **Hours** - Number of hours to delay before completing the loop.
2. **Minutes** - Number of minutes to delay before completing the loop.
3. **Seconds** - Number of seconds to delay before completing the loop.
4. **Current Loop Count** - The number of times the workflow has looped so far.
5. **Max Loop Count** - The maximum number of times the workflow is allowed to loop before failing.

## Workflow Process
1. **Check Max Loops:**
   - If the **Current Loop Count** is greater than or equal to the **Max Loop Count**, the workflow outputs a failure and stops execution.
2. **Apply Delay:**
   - If the **Current Loop Count** is less than the **Max Loop Count**, the workflow delays execution based on the specified **Hours, Minutes, and Seconds**.
3. **Increment and Output:**
   - The workflow increments the **Current Loop Count** and then outputs a success with the new loop count.
   - It will not start looping again automatically; the workflow must be triggered again as a sub-workflow to continue looping.

## Usage 
To use this workflow:
1. Provide the required input values.
2. Ensure that the **Max Loop Count** is set to a reasonable value to prevent unnecessary looping.
3. Monitor the workflow to ensure that it behaves as expected in failure scenarios.

## Example
Assume the following input values:
- **Hours:** `0`
- **Minutes:** `5`
- **Seconds:** `0`
- **Current Loop Count:** `0`
- **Max Loop Count:** `3`

The workflow will:
1. Check if `0 >= 3` (false, so it proceeds).
2. Delay for 5 minutes.
3. Increment the loop count to `1` and output success.
4. The workflow stops and must be triggered again as a sub-workflow to continue.
5. Repeat the process until the count reaches `3`, at which point it will fail.

## Tips
- **Use Multiplication for Dynamic Delays:**
  - This workflow can be made more powerful by increasing the delay with each loop.
  - Instead of using a static delay, leverage the **Current Loop Count** (`{{ CTX.whatever_your_loop_count_is }}`) to dynamically adjust the delay.
  - Example: If your initial delay is 10 minutes, you can multiply it by the loop count to exponentially increase the delay:
    ```text
    {{ CTX.whatever_your_loop_count_is * 10 }}
    ```
  - This format would then increase the delay by ten minutes with every loop.
  - This method allows for a more adaptive retry mechanism, reducing resource usage while waiting for system recovery.

## Notes
- Ensure that the delay values are appropriate for the expected outage duration.
- This workflow is useful for handling temporary failures where retrying might resolve the issue.
- If persistent failures occur, additional error handling should be implemented outside this loop.

## License
This workflow is provided under the MIT License. Feel free to modify and use it according to your needs.
