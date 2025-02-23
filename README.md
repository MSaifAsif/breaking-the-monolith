# The What and the Why
Have you ever tried to rearrange your entire living room and ended up knocking over a lamp or two in the process? That is exactly what it can feel like when you try to break apart a huge code repository. You think you are going to make everything look neat and tidy, but you might just end up with code everywhere. In this post, I will share my personal approach to preparing for a project like this. I am definitely not claiming to be the ultimate expert, so please keep in mind that these are just my own thoughts. I hope they bring you a smile, a bit of helpful guidance, and maybe a nudge in the right direction before you get lost in the tangled maze of a giant codebase.

```Python
                           +---------------------------------------------------------+
                           |    "A Personal Guidebook for Splitting the Large       |
                           |                 Code Repository"                        |
                           +---------------------------------------------------------+
                                      |
                                      |
                                      |
         Developer A (@_@): "Let me check this book
                  so I know where to start!"
                                      |
                                      |
                          Developer B (O.o): "Yes, we need
                                       all the help we can get!"
                                      |
                                      v
             +------------------+                  +----------------------+
             | Step 1: Why?    |                  | Step 2: Inspect      |
             | Step 3: Map     |                  | Step 4: Skills       |
             | Step 5: Plan    |                  | Step 6: Data         |
             +------------------+                  +----------------------+
               Developer A: "Aha!"                      Developer B: "Got it!"
                                      |
                                      v
               +-------------------------------------------------------+
               |                 MONOLITHIC CODEBASE                   |
               |       (Huge, Overgrown, All-in-One Monster)           |
               +-------------------------------------------------------+
                           |                            |
      Developer A: "We will follow the       Developer B: "Yes, let's tame
      book and figure out exactly which       this monster step by step!"
      pieces to slice out first."         
                           |
                           |
               Product Manager (^-^): "Please do not break
                  everything in the process!"
                           |
                           |
                           v
             +-------------------------------------------------+
             | Step 7: Testing,   Step 8: Release,             |
             | Step 9: Extraction, Step 10: Final Approval      |
             +-------------------------------------------------+
                           |
                           |
      Developers (A & B): "We have our roadmap and a good idea. Time to get it done!"

```

## 1. Describe the Main Reason and Goal of the Project

**What is this step about?**  
You begin by explaining the main reason you want to move away from a single large code repository. This might include faster development, easier maintenance, or being able to update individual parts of the system without risking the entire application. It is very important that everyone in your group has a clear idea of why you are doing this.

**Why is this step first?**  
When you know exactly why you want to split the large code repository, you can make better decisions later. If everyone shares the same goals, it makes the whole journey smoother.

**What do you do in this step?**  
1. Write down the main problems you are facing with the existing large code repository, such as slow deployments or tangled code.
2. Explain the main benefits you expect from splitting the code, such as quicker updates or fewer bugs in unrelated areas.
3. Talk to all team members, managers, and anyone else who cares about the project. Make sure they agree on the goals.

**How does the size of the repository affect this step?**  
If the repository is very large, it can be more difficult to explain all the issues because there are often many problems hidden in different places. It may take longer to gather everybody’s thoughts if the codebase is huge or if multiple teams work on different parts. If it is smaller, you can usually list the reasons and benefits very quickly.

**What is your main deliverable at this point?**  
You should have a written statement of your goals and expected benefits. Everyone should review this and give a thumbs up before you move on.

---

## 2. Review the Structure of the Current Code

**What is this step about?**  
Now you take a close look at how your code is organized today. This includes identifying the main sections or modules, what they do, and how they depend on each other. It also means understanding where your biggest performance issues or bugs are coming from.

**Why is this step important at this stage?**  
You cannot break something apart safely if you do not understand how it is built in the first place. By mapping out the code, you will be able to see which parts can be separated and which parts are deeply connected.

**What do you do in this step?**  
1. Make a list of the major parts or modules of your code. For example, if your application handles online orders, you might have sections for user accounts, shopping carts, payments, and so on.  
2. Draw a simple diagram showing how these different sections talk to each other. This can be done with boxes and lines.  
3. Take note of where the code might have hidden connections. For example, does the shopping cart system also rely on user account data in a way that is not obvious?

**How does the size of the repository affect this step?**  
A larger repository can have hundreds of files or even thousands, which makes it harder to create a clear map of what is connected to what. It may require extra tools or more people to look at different parts of the code. In a smaller repository, you might be able to do this by hand fairly quickly.

**What is your main deliverable at this point?**  
You should have at least one document that shows how your code is structured. It does not need to be very fancy, but it should help anyone on the team quickly see which modules exist and how they relate to each other.

---

## 3. Identify the Different Parts of the Business Logic

**What is this step about?**  
Here, you figure out which major parts of the code match up with specific business functions. For example, does one part of the system handle payments, does another handle product listings, and is there yet another that takes care of user registrations?

**Why do this now?**  
When you decide how to split the big code repository, it often helps to separate it by business function rather than by technical layers. This makes it easier for teams to focus on a single business area and reduces confusion.

**What do you do in this step?**  
1. Make a list of all the functions or tasks that the application handles. Include things like creating an order, sending an invoice, giving a refund, and so on.  
2. Group these tasks into categories that make sense. For instance, tasks that deal with user management in one group, and tasks that deal with product inventory in another group.  
3. Decide which group feels easiest to separate first. Perhaps you choose the one that offers the biggest benefit if it is taken out of the large repository.

**How does the size of the repository affect this step?**  
A large repository often has many more business functions spread out in many files. It can be overwhelming to figure out everything at once, so it might help to break it down and focus on only a few functions at a time. Smaller repositories are usually simpler and might only have a few core functions.

**What is your main deliverable at this point?**  
You end up with a clear list of business functions and a rough idea of which ones can be grouped together if you eventually move them into their own smaller service.

---

## 4. Check the Skills Your Team Has

**What is this step about?**  
This step is all about looking at what the team knows and what the team may not know. Splitting a big code repository into smaller services often involves new tools, new ways of deploying code, and new ways of testing.

**Why do this before moving forward?**  
If nobody on the team is comfortable with, for example, creating new containers for each service or setting up a testing pipeline, the process may slow down or fail. By checking for skill gaps early, you can plan for training or bring in outside help.

**What do you do in this step?**  
1. Ask your team members if they have experience with building smaller services, deploying them, and monitoring them.  
2. Identify any topics that make people uncertain, such as new database technology or ways to set up the environment.  
3. Make a plan to help people learn. This could be through workshops, pairing new developers with experienced ones, or giving people some time to research on their own.

**How does the size of the repository affect this step?**  
A very large repository often means you have a bigger team or multiple teams. Each team might need different levels of training because the repository covers so many business domains. With a smaller repository, you might have a smaller team, so it could be easier to share knowledge and skills.

**What is your main deliverable at this point?**  
You should have a list of the training sessions or documents the team will need before the work of splitting the repository can begin. You might also create a timeline for any training so that everyone is prepared.

---

## 5. Draw a Picture of How You Want the New Setup to Look

**What is this step about?**  
This step is where you imagine and sketch out how the new, smaller services will connect and communicate once you begin splitting the large repository. Think of it as a roadmap for where you want to go.

**Why is this helpful before coding?**  
When people can see a simple diagram or picture of how the new system will be organized, it is much easier to understand what they need to build. It also prevents confusion about which part depends on which other part.

**What do you do in this step?**  
1. Take the groups of business functions you identified earlier. Turn each group into a box in a diagram.  
2. Draw lines or arrows to show where information flows from one box to another.  
3. Mark which data will be stored in each box, and which outside systems it might talk to.

**How does the size of the repository affect this step?**  
If your current repository is very large, then your new diagram may have many boxes and connections, which can get complicated. You might want to break the diagram into sections. With a smaller repository, you might only need one or two boxes to represent your new services.

**What is your main deliverable at this point?**  
A diagram that shows the target state of your system with separate services. This diagram can be shared with all team members so that everyone knows what the plan is.

---

## 6. Figure Out How to Handle Your Data

**What is this step about?**  
You need to decide how to move or separate your databases when you split your code. If you keep one big database, you might not get the full benefits of having smaller services. If you split the database, you must figure out how to handle shared tables.

**Why is this step important now?**  
Data is often the trickiest part of breaking something into smaller pieces. If you do not plan this carefully, you might end up with missing records or parts of the system that do not work together.

**What do you do in this step?**  
1. Make a list of your tables or data structures and note which business function they belong to.  
2. Plan if each new service will have its own database or if some services will share a database at first.  
3. Think about how to keep things running while you move data around. Some teams use techniques to copy data in the background so the old system can still work.

**How does the size of the repository affect this step?**  
If your codebase is very large, you might also have a huge database with many tables. Splitting the database might require a lot of planning and time, especially if there are many hidden connections between tables. With a smaller codebase, the data is usually simpler, so this process is not as overwhelming.

**What is your main deliverable at this point?**  
A clear plan for how you will handle the data during and after the split. This should include what to do if something goes wrong, like a backup plan or a way to roll back changes.

---

## 7. Make a Plan for Testing

**What is this step about?**  
When you split your code into smaller services, you need to make sure you still test everything properly. You will likely need new tests that check each service on its own, plus tests that check how services work together.

**Why is this step important now?**  
If you wait until you have already split the code to figure out testing, you could end up missing important checks. Planning how you will test early on makes sure you do not skip anything.

**What do you do in this step?**  
1. Review your current tests to see which ones can be reused.  
2. Decide if you need new types of tests, such as tests that verify how two separate services exchange information.  
3. Plan your testing environments. For example, you might have a special environment just for testing these separate services before combining them with the old code.

**How does the size of the repository affect this step?**  
Larger repositories often mean more tests. You might also have more dependencies to mock or fake during testing. This can make the testing plan bigger and more complicated. Smaller repositories might only need a few tests to cover the main features.

**What is your main deliverable at this point?**  
A document or plan explaining how you will test each part of the new system. This should include the specific steps you will take to make sure the new services are reliable.

---

## 8. Get Your Process for Building and Deploying Code Ready

**What is this step about?**  
Sometimes called a pipeline for continuous integration and delivery, this is the process you use to automatically build, test, and release your code. You want to make sure you can do this for each new service without confusion.

**Why do you need this step before splitting the code?**  
When you split the code, you will have several smaller projects instead of one large one. Each smaller project will need to be built and tested on its own. If your current process is built around one large project, it may not work for multiple smaller ones.

**What do you do in this step?**  
1. Look at your current build scripts and see if they assume there is only one repository.  
2. Adjust your building and releasing process so that it can handle multiple repositories, each with its own build steps.  
3. Make sure your team knows how to use this new process and that it is well documented.

**How does the size of the repository affect this step?**  
A larger repository may have a more complex or specialized process for building and releasing. This might require a big effort to break it apart. Smaller repositories tend to have simpler build scripts, so you might be able to adapt things quickly.

**What is your main deliverable at this point?**  
You should have a working setup that can build and deploy each new service separately, as well as the original code if needed. Everyone on the team should know how to use it.

---

## 9. Write Down a Detailed Plan for Which Parts You Will Split First

**What is this step about?**  
At this point, you have a clear picture of what you want to achieve, how your data will be handled, how you will test, and how you will build and release your new services. Now you need to make a roadmap that says which part of the code you will split out first, which part you will do second, and so on.

**Why is it done now?**  
You have gathered all the knowledge you need to decide on the safest and most beneficial order for splitting your code. Doing it too soon might mean you make incorrect choices. Doing it too late might lead to confusion.

**What do you do in this step?**  
1. Pick the part of the code that should be moved first. This might be the easiest part or the one that will give you the biggest benefit if you separate it.  
2. Write down roughly how long it will take and which people will work on it.  
3. Create a list of risks. For example, if you are splitting the order management system first, note that it might break the payment process if not done carefully.

**How does the size of the repository affect this step?**  
If the repository is very large, there may be many possible places to start. You might need to split out small sections over multiple months or even years. In a smaller repository, you might do it in a few weeks.

**What is your main deliverable at this point?**  
A clear written plan or roadmap that everyone agrees on. It might look like a timeline or a list of steps, each with an expected date and the people in charge.

---

## 10. Make Sure Everyone Agrees on the Plan

**What is this step about?**  
Before you begin coding, it is wise to meet with everyone involved one last time to check that the plan makes sense, that there are no surprises, and that everyone knows their role.

**Why is this step important?**  
Any big change can affect people in different roles, such as quality assurance workers, product managers, or customer support teams. If they are not aware of what is happening, the process can be delayed or even stopped.

**What do you do in this step?**  
1. Organize a meeting where you walk through the final roadmap and explain the timeline and expected results.  
2. Listen to feedback. If someone points out a problem, try to fix it or note it for later.  
3. Get a clear agreement from everyone that it is okay to start with the actual splitting of the code.

**How does the size of the repository affect this step?**  
If your repository is huge and involves many teams, you might need multiple meetings or a large virtual conference to reach everyone. A smaller repository might only require one short meeting with a few people.

**What is your main deliverable at this point?**  
You end up with a shared understanding and acceptance of the plan. There should be a simple record, such as a document or note from the meeting, stating that everyone agrees.
