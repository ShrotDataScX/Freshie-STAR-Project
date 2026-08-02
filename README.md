# Freshie STAR Project – Repository Workflow

## Repository Maintainer

**Repository Architect & Maintainer:** **Shrot**

Responsibilities:

* Design and maintain the repository structure.
* Create and maintain branches.
* Define development workflow.
* Manage repository settings and branch protection.
* Integrate feature branches into `develop`.
* Merge stable releases into `main`.

---


## General guide - 
Everybody make your own branch and work on that ( do not directly push to main branch )
After you are sure about work and have compared amongst the other perception peeps , create a pull request.

## We'll start by simulating pre built Turtlebot3 burger model ;
We can use fusion360 to convert it into xacro(xml) file and then use gazebo plugins in that file to complete simulation
and then we'll proceed to hardware implementation.

You can import the Initial burger.STEP file in fusion360 to view turtlebot3

https://github.com/ShrotDataScX/turtlebot3_simulations

https://github.com/ShrotDataScX/turtlebot3

Above links are of official documentation of turtlebot3 ; you can clone these repos to see how does the workspace looks like when we do simulation
# Branch Ownership

Each subsystem has a designated owner responsible for reviewing Pull Requests, ensuring code quality, and coordinating development within that subsystem.

| Branch                    | Owner / Reviewer |
| ------------------------- | ---------------- |
| `feature/perception`      | **Priyanshu**    |
| `feature/motion-planning` | **Aayush**       |
| `feature/controls`        | **Shrot**        |
| `feature/hardware`        | **Tushar**        |
| `feature/testing`         | **Ritanya**        |
| `feature/documentation`   | **Saanvi**        |
| `develop`                 | **Shrot**        |
| `main`                    | **Shrot**        |



---

# Team Responsibilities

## Perception Team

| Member    | Responsibility                                       |
| --------- | ---------------------------------------------------- |
| Priyanshu | Robot Description (URDF/Xacro, TF Tree, Robot Model) |
| Shrot     | SLAM Toolbox Integration                             |
| Ritanya   | Camera Simulation & Integration                      |
| Saanvi    | LiDAR Integration                                    |
| Tushar    | Gazebo Sensor Plugins                                |
| Aayush    | Perception Launch & Integration                      |

---

## Motion Planning Team

| Member | Responsibility   |
| ------ | ---------------- |
| Aayush | Nav2 Integration |
| Saanvi | Global Planner   |
| Tushar | Local Planner    |

---

## Controls & Reinforcement Learning Team

| Member    | Responsibility         |
| --------- | ---------------------- |
| Priyanshu | PID Controller         |
| Shrot     | Reinforcement Learning |
| Ritanya   | Controller Interface   |

---

# Repository Structure

```
main
│
└── develop
    │
    ├── feature/perception
    │   ├── perception/priyanshu/robot-description
    │   ├── perception/shrot/slamtoolbox
    │   ├── perception/ritanya/camera
    │   ├── perception/saanvi/lidar
    │   ├── perception/tushar/gazebo-sensors
    │   └── perception/aayush/perception-launch
    │
    ├── feature/motion-planning
    │   ├── motion/aayush/nav2
    │   ├── motion/saanvi/global-planner
    │   └── motion/tushar/local-planner
    │
    ├── feature/controls
    │   ├── controls/priyanshu/pid
    │   ├── controls/shrot/rl
    │   └── controls/ritanya/controller-interface
    │
    ├── feature/hardware
    │
    ├── feature/testing
    │
    └── feature/documentation
```

---

# Development Workflow

Every task follows the same workflow.

```
Personal Branch
        │
        ▼
Feature Branch
        │
        ▼
develop
        │
        ▼
main
```

### Workflow Steps

1. Pull the latest changes from the parent branch.
2. Work only on your assigned personal branch.
3. Commit frequently with meaningful commit messages.
4. Push your branch to GitHub.
5. Open a Pull Request into the corresponding **feature branch**.
6. The feature owner reviews and approves the Pull Request.
7. The repository maintainer merges completed feature branches into `develop`.
8. After successful integration and testing, `develop` is merged into `main`.

---

# Branch Responsibilities

## `main`

* Stable
* Demo-ready
* Competition-ready
* Hardware verified
* No direct commits

---

## `develop`

* Integration branch
* Receives completed feature branches
* Used for full-system testing
* May contain work in progress
* No direct feature development

---

## `feature/*`

Subsystem integration branches.

Examples:

* Perception
* Motion Planning
* Controls
* Hardware
* Testing
* Documentation

Each subsystem owner is responsible for reviewing and maintaining code quality within these branches.

---

## Personal Branches

Every contributor develops only in their assigned branch.

Examples:

* `perception/shrot/slamtoolbox`
* `motion/aayush/nav2`
* `controls/priyanshu/pid`

Personal branches should never be merged directly into `develop` or `main`.

---

# Pull Request Rules

* No direct commits to `main`.
* No direct commits to `develop`.
* Every change must go through a Pull Request.
* Every Pull Request must be reviewed by the corresponding subsystem owner.
* Merge conflicts should be resolved in the source branch before approval.
* Keep Pull Requests focused on a single feature or task.

---

# Branch Protection

Protected branches:

* `main`
* `develop`

Recommended protections:

* Pull Request required before merging.
* Required approvals before merging.
* No direct pushes.
* Prevent accidental branch deletion.
* Automatically delete merged personal branches after successful integration.

---

# Commit Message Guidelines

Use concise, descriptive commit messages.

Examples:

```
feat: add Gazebo LiDAR plugin

fix: correct wheel TF transform

docs: update simulation setup guide

refactor: reorganize robot_description package

test: add SLAM Toolbox integration tests
```

---

# Goal

The objective of this workflow is to:

* Maintain a clean and organized repository.
* Minimize merge conflicts.
* Enable parallel development across multiple subsystems.
* Keep `main` stable at all times.
* Ensure every contribution is reviewed before integration.





# Let's Kill this !!!!!!
