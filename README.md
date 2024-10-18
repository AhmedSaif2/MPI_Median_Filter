# Median Filter with MPI

This project implements a parallel median filter (smoothing filter) using the MPI (Message Passing Interface) library to significantly reduce the time needed to apply the filter. The median filter is commonly used in image processing to remove noise while preserving edges. By distributing the computational workload across multiple processors, this implementation achieves faster processing times compared to a sequential approach.


# Installation 
To set up the project on your local machine, follow these steps:

1. **Install MPI Library:** Ensure that you have MPI installed on your system. You can download MPI from [Here](https://www.microsoft.com/en-us/download/details.aspx?id=57467).

2. **Clone this repository:**

```bash
git clone https://github.com/AhmedSaif2/MPI_Median_Filter.git
```
3. **Open in Visual Studio:**

    - Open the solution file (.sln) in Visual Studio.
    - Make sure MPI is set up in your Visual Studio environment.

4. **Build the project:**

    - Configure your project to use MPI libraries.
    - Build and run the solution.

# Usage
1. **Navigate to the .exe file:** After building the project, navigate to the directory where the executable (.exe) file is located.

2. **Open the terminal:** Open a terminal or command prompt in that directory.

3. **Run the program using MPI:** Use the mpiexec command to run the program on multiple processors. Example:

```bash
mpiexec -n 4 MPI_Median_filter.exe
# This command runs the filter using 4 processors 
```

4. **Input:**
    - The program takes the window size and number of images as input.
5. **Output:**
    - The resulting smoothed image is saved to the specified output file.

# Results
By distributing the workload across multiple cores, the performance improves significantly as the number of processors increases. Below are the results from running the filter using 5 as the window size and 1 only image:

- 1 Core: 44 seconds
- 4 Cores: 16 seconds
- 12 Cores: 11 seconds

The difference in speed becomes more noticeable as the number of images processed increases. Here are the results from running the filter using 5 as the window size but increasing the number of images to 4:

- 1 Core: 170 seconds (baseline)
- 4 Cores: 63 seconds (improvement observed)
- 12 Cores: 41 seconds (significant performance boost)
