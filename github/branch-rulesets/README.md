<!-- omit in toc -->
# Branch Rule Sets Documentation

- [Description](#description)
- [Rule Sets](#rule-sets)
  - [Rule: Default](#rule-default)
  - [Rule: Protect main branch](#rule-protect-main-branch)

## Description

This documentation provides detailed information about the branch rule sets configured in this repository. Branch rule sets are used to enforce specific rules and conditions on branches to ensure code quality and maintain a clean and organized repository. These rules can include requirements for commit signatures, merge strategies, and pull request reviews.

## Rule Sets

### Rule: Default

<!-- omit in toc -->
#### Name
**Default**

<!-- omit in toc -->
#### Target
**Branch**

<!-- omit in toc -->
#### Enforcement
**Active**

<!-- omit in toc -->
#### Description
This rule set applies to all branches in the repository, including the default branch. It enforces non-fast-forward merges and requires commits to be signed.

<!-- omit in toc -->
#### Conditions
- **ref_name**
  - **exclude:** No branches are excluded from this rule set.
  - **include:** 
    - `~DEFAULT_BRANCH`: This includes the default branch of the repository.
    - `~ALL`: This includes all branches in the repository.

<!-- omit in toc -->
#### Rules
1. **non_fast_forward**: This rule prevents non-fast-forward merges, ensuring that the branch history is always linear.
2. **required_signatures**: This rule requires that all commits are signed with a GPG key.

<!-- omit in toc -->
#### Bypass Actors
**None**: No users or teams are allowed to bypass these rules.

---

### Rule: Protect main branch

<!-- omit in toc -->
#### Name
**Protect main branch**

<!-- omit in toc -->
#### Target
**Branch**

<!-- omit in toc -->
#### Enforcement
**Active**

<!-- omit in toc -->
#### Description
This rule set is specifically designed to protect the main branch of the repository. It enforces non-fast-forward merges, requires commits to be signed, prevents branch deletion, and sets up specific pull request requirements.

<!-- omit in toc -->
#### Conditions
- **ref_name**
  - **exclude:** No branches are excluded from this rule set.
  - **include:** 
    - `~DEFAULT_BRANCH`: This includes the default branch of the repository.

<!-- omit in toc -->
#### Rules
1. **non_fast_forward**: This rule prevents non-fast-forward merges, ensuring that the branch history is always linear.
2. **required_signatures**: This rule requires that all commits are signed with a GPG key.
3. **deletion**: This rule prevents the deletion of the branch.
4. **pull_request**: This rule sets up specific requirements for pull requests:
   - **required_approving_review_count:** 0: No minimum number of approving reviews is required.
   - **dismiss_stale_reviews_on_push:** true: Dismisses stale reviews when new commits are pushed to the pull request.
   - **require_code_owner_review:** true: Requires a review from a code owner.
   - **require_last_push_approval:** false: Does not require approval for the last push.
   - **required_review_thread_resolution:** false: Does not require all review threads to be resolved.
   - **automatic_copilot_code_review_enabled:** true: Enables automatic code review by GitHub Copilot.
   - **allowed_merge_methods:**
     - `merge`: Allows merging pull requests with a merge commit.
     - `squash`: Allows merging pull requests by squashing commits.
     - `rebase`: Allows merging pull requests by rebasing commits.

<!-- omit in toc -->
#### Bypass Actors
**None**: No users or teams are allowed to bypass these rules.