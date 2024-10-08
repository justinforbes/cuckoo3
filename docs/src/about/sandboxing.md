# Sandboxing
As defined by Wikipedia, "in computer security, a sandbox is a security mechanism for separating running programs. It is often used to execute untested code or untrusted programs from unverified third parties, suppliers, untrusted users, and untrusted websites.".

This concept applies to malware analysis's sandboxing too: our goal is to run an unknown and untrusted application or file inside an isolated environment and get information on what it does.

Malware sandboxing is a practical application of the dynamical analysis approach: instead of statically analyzing the binary file, it gets executed and monitored in real-time.

This approach obviously has pros and cons, but it's a valuable technique to obtain additional details on the malware, such as its network behavior. Therefore, it's a good practice to perform both static and dynamic analysis while inspecting malware in order to gain a deeper understanding of it.

Simple as it is, Cuckoo is a tool that allows you to perform sandboxed malware analysis.

## Using a Sandbox
Before starting to install, configure, and use Cuckoo, you should take some time to think about what you want to achieve with it and how.

Some questions you should ask yourself:

What kind of files do I want to analyze?
What volume of analyses do I want to be able to handle?
Which platform do I want to use to run my analysis on?
What kind of information do I want about the file?
The creation of the isolated environment (for example, a virtual machine) is probably the most critical and important part of a sandbox deployment; it should be done carefully and with proper planning.

Before getting hands on the virtualization product of your choice, you should already have a design plan that defines:

Which software to install and which versions (particularly important when analyzing exploits).
Consider that automated malware analysis is not deterministic and its success might depend on a trillion factors: you are trying to make malware run in a virtualized system as it would do on a native one, which could be tricky to achieve and may not always succeed. Your goal should be both to create a system able to handle all the requirements you need as well as try to make it as realistic as possible.

For example, you could consider leaving some intentional traces of normal usage, such as browsing history, cookies, documents, images, etc. If malware is designed to operate, manipulate, or steal such files, you'll be able to notice it.

Virtualized operating systems usually carry a lot of traces with them, which makes them very easily detectable. Even if you shouldn't overestimate this problem, you might want to take care of this and try to hide as many virtualization traces as possible. There is a lot of literature on the Internet regarding virtualization detection techniques and countermeasures.

Once you finish designing and preparing the prototype of the system you want, you can proceed with creating it and deploying it. You will always be in time to change things or slightly fix them, but remember that good planning at the beginning always means fewer troubles in the long run.
