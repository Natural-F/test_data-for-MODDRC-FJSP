# test_data-for-MODDRC-FJSP
test_data for MODDRC-FJSP

# Dataset Documentation (README)

## Dataset Overview
This dataset is generated for the multi-objective dynamic dual-resource constrained flexible job shop scheduling problem
(MODDRC-FJSP) with worker assignment. It contains instances of various sizes, each including information about machines, workers, jobs, processing times, and other key parameters.

## Data Fields Description

### `Processing_time`
- **Definition**: Processing time for each operation of each job on different machines by different workers
- **Data Structure**: Four-dimensional list [job][operation][machine][worker]
- **Note**: If a machine cannot process an operation, the value is -1; otherwise, it's a dictionary mapping worker IDs to processing times ranging from [1,50]

### `A1`
- **Definition**: Arrival times for all jobs
- **Data Structure**: One-dimensional list
- **Note**: Initial jobs have arrival time 0, new jobs have arrival times generated from an exponential distribution

### `M_num`
- **Definition**: Total number of machines
- **Data Structure**: Integer
- **Note**: Machines are numbered from 0 to M_num-1

### `Op_num`
- **Definition**: Number of operations for each job
- **Data Structure**: One-dimensional list
- **Note**: Each job's operation count is randomly generated within range [1,20]

### `J`
- **Definition**: Mapping from job index to its number of operations
- **Data Structure**: Dictionary
- **Note**: Keys are job indices, values are operation counts

### `O_num`
- **Definition**: Total number of operations across all jobs
- **Data Structure**: Integer
- **Note**: Sum of all jobs' operation counts

### `J_num`
- **Definition**: Total number of jobs
- **Data Structure**: Integer
- **Note**: Initial jobs (5) + new inserted jobs

### `W`
- **Definition**: List of workers
- **Data Structure**: One-dimensional list
- **Note**: Workers are numbered from 0 to W_num-1

### `W_k`
- **Definition**: Subsets of workers assigned to each machine
- **Data Structure**: Two-dimensional list [machine][worker]
- **Note**: Each machine is assigned 1-5 workers, not exceeding total worker count

### `W_cost`
- **Definition**: Unit time cost for each worker
- **Data Structure**: One-dimensional list
- **Note**: Each worker's cost is randomly generated within range [10,50]

### `W_rest`
- **Definition**: Rest time for each worker
- **Data Structure**: One-dimensional list
- **Note**: Each worker's rest time is randomly generated within range [300,1000]

### `W_threshold`
- **Definition**: Threshold time for each worker
- **Data Structure**: One-dimensional list
- **Note**: Each worker's threshold is randomly generated within range [300,1000]



## Usage Instructions
These datasets can be used to test scheduling algorithms for job shop problems of different scales, especially those considering worker assignment. Processing times depend on both machine and worker combinations, reflecting the complexity of real production environments.
