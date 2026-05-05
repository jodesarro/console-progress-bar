# Console Progress Bar: A C code for printing the progress of numeric iterations on the console

## Available features

### Print the progress bar

<details>
  <summary>
    <code><b>print_progress_bar(iteration_current, iteration_total)</b></code>
  </summary>

  - **Description:** Print a progress bar for an iteration process.
  - **Parameters:**
    - `iteration_current`, the number of the current iteration.
    - `iteration_total`, the total number of iterations.
  - **Implementation:** It prints a progress bar with a percentage evaluated
  through `100 * iteration_current / iteration_total`.
</details>

### Print the progress bar at a fixed percentage interval

<details>
  <summary>
    <code><b>print_progress_bar_every_percent(iteration_current, iteration_total, percent)</b></code>
  </summary>

  - **Description:** Print a progress bar at a fixed percentage interval.
  - **Parameters:**
    - `iteration_current`, the number of the current iteration.
    - `iteration_total`, the total number of iterations.
    - `percent`, the percentage interval.
  - **Implementation:** It calls `print_progress_bar(iteration_current, iteration_total)`
  at every `percent` of percentage.
</details>

### Print a progress of 0%

<details>
  <summary>
    <code><b>print_progress_bar_empty()</b></code>
  </summary>

  - **Description:** Print an empty progress bar for a 0% progress.
  - **Implementation:** It calls `print_progress_bar(0, 0)`.
</details>

### Print a progress of 100%

<details>
  <summary>
    <code><b>print_progress_bar_full()</b></code>
  </summary>

  - **Description:** Print a full progress bar for a 100% progress.
  - **Implementation:** It calls `print_progress_bar(1, 1)`.
</details>

## How to use

This code is header‑only, meaning there is nothing to build.

You only need to paste all the content of the
[include](include/) folder inside the include folder of your project (if you do not have an include
folder in your project, paste the content inside the root folder of your
project).

Finally, just write `#include "console-progress-bar.h"` at the very
beginning of your code and you shall be ready to use the functions.

## A simple example

### Input

```
#include "../include/console-progress-bar.h"
#include <unistd.h> /* Required for sleep() */

int main() {

  /* Printing a progress of 0% */
  print_progress_bar_empty();

  /* Loop for printing the progress after each iteration */
  for (int i = 0; i <= 98; i++) {
    sleep(1); /* Waiting one second, simulating a slow process */
    print_progress_bar(i, 100); /* Printing the progress */
  }

  /* Printing a progress of 100% */
  print_progress_bar_empty();
}
```

## Some C details

In this project, the implementation is carried out in terms of the C99
standards.

## Authorship

The codes and routines was developed and is updated by
<a href="https://www.researchgate.net/profile/Jhonas-de-Sarro">
Jhonas O. de Sarro</a> ([@jodesarro](https://github.com/jodesarro)).

## Licensing

This project is protected under [MIT License](LICENSE).