# hapjs RFC

Most code changes for feature updates and bug fixes can follow the normal GitHub Flow process and be completed by submitting a pull request and undergoing code review. However, some updates may cause fundamental changes to the system architecture and APIs - for these types of updates, we need to design a process to ensure consensus between the hapjs team and the community.

RFC (Request for Comments) is a process mechanism designed to ensure that significant feature updates and architectural changes can be smoothly advanced.

## Which types of changes require the RFC process

As mentioned earlier, any change that causes changes to the system architecture or APIs or causes changes to the overall code structure requires the RFC process, for example:

- Adding a package that needs to be installed by developers
- Modifying API parameters or deleting APIs
- Changing the scheme for hapjs's established development practices
- Any changes that render published versions unusable

The following types of changes do not require the RFC process:

- Bug fixes
- Feature iterations that do not affect the use of published versions
- Adding or deleting warnings
- Internal architecture adjustments or code refactoring
- Performance improvements or compatibility improvements

If a developer submits a pull request that should go through the RFC process, the hapjs team will close the pull request and ask the developer who submitted the pull request to execute the RFC process in the RFC repository.

## Why do we need the RFC process?

Cumbersome processes are undoubtedly harmful to development and iteration efficiency, but for the following reasons, let us introduce the RFC mechanism even if we are willing to reduce iteration efficiency:

1. Stability. The existing RFC process can minimize the impact of each iteration on old users as much as possible. The RFC process is also tied to a certain extent with version releases to ensure that hapjs iterations comply with semantic versioning specifications as much as possible.
2. Openness and transparency. We hope that hapjs iterations are as open, public, and transparent as possible, and that everyone can participate in the RFC discussion and influence the next version of hapjs. At the same time, we also hope to increase the participation of the hapjs community through this and let more people participate in the core construction of hapjs.
3. Code quality. The existing RFC process requires a design document before implementation, which is very helpful for specific code implementation.
4. Design tracking. We hope that every RFC document and the PR behind it can reflect the thinking and compromise behind adding, canceling, or modifying a feature, which is very important for the long-term development of hapjs and developers who want to delve into hapjs.

## RFC process mechanism

In short, if the RFC change needs to be released in future hapjs versions, the RFC proposal document needs to be merged in the RFC repository first.

- Fork hapjs RFC repository: #TODO;
- Copy `0000-template.md` to `rfcs/0000-my-feature.md` (`my-feature` needs to be changed to a word that can describe the RFC, and `0000` is the RFC number, which does not need to be changed for now);
- Fill in the RFC proposal according to the template in active/0000-my-feature: The RFC needs to describe the motivation and reasons clearly, show specific cases and design details, and the possible problems. The RFC proposal enters the `Pending` stage;
- Submit a pull request to hapjs RFC repository. At this stage, hapjs team and the community will discuss the RFC proposal together;
- When the RFC proposal reaches consensus in the community, the RFC proposal enters the `Active` stage;
- The code implementation of the RFC proposal is merged into the hapjs main repository, and the RFC proposal enters the `Landed` stage. The RFC proposal is also merged into the RFC repository;
- Finally, the hapjs team will decide which version to release the RFC proposal changes.

## RFC proposals in the `Pending` stage

When an RFC proposal is submitted as a pull request:

- The RFC proposal will be discussed by the hapjs team and the community together, and the details and conclusions finally obtained may not be consistent with the initial RFC proposal;
- The RFC proposal may be rejected due to failure to reach consensus, and at least one member of the hapjs team will give the reason for rejection;
- When the RFC proposal reaches consensus in the community, it enters the `Active` stage, and the hapjs team or the community can begin to implement the proposal's code;
- The RFC proposal may fail to reach consensus due to no discussion, and the hapjs team can decide whether to accept the proposal based on the actual situation.

## RFC proposals in the `Active` stage

When an RFC proposal reaches consensus in the community and enters the `Active` stage, it does not mean that the changes proposed in the RFC proposal are set in stone, and the code implementation of the RFC proposal may not be merged into the hapjs main repository. However, when the RFC proposal enters the `Active` stage, it does mean that the hapjs team and the community recognize the changes proposed in the RFC proposal and believe that this is something that should be implemented in the future.

That is to say, when an RFC proposal enters the `Active` stage, it does not mean that this change has been assigned a priority, and the specific release time also needs to be determined after the code implementation.

## Implementation of RFC proposals

The author of the RFC proposal document is not obligated to implement the RFC proposal code. Of course, if the author of the RFC proposal (or any developer) is willing to implement the code after the RFC proposal document is accepted, this is also very welcome.

Accepted RFC proposals need to include a pull request link in the hapjs main repository (even if the PR is still being drafted or incomplete), and the author of the RFC proposal and the hapjs team need to urge the RFC implementation PR to move in the direction described in the RFC proposal document.

The hapjs RFC process mechanism is inspired by Taro RFC, Rust RFC Process, React RFC Process, and Vue RFC Process.
