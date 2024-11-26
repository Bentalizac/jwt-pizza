Topic: When should cloud-based automation be used?

Going through this class one of my projects at work involves managing inventory of various 
devices and keeping this up to date across multiple management systems. One of the primary sources of toil is checking and updating the status of the remote management of our MacBooks for rent, which are retired to us by the rest of campus. As we get these MacBooks, they are inventoried in a ServiceNow database, but it is incredibly rare for the sending department to update BYU's Apple School Management tools to show that Surplus is now the controlling department. This causes issues for imaging rental devices and is generally a pain to deal with. To solve this problem, our manager needs a list of serial numbers from the received devices, and needs to manually update the status of each device. At the beginning of the semester, we were also manually reading off and adding these serial numbers to an Excel spreadsheet in our office server on the local network. We moved over to using an Excel sheet in Box partway through the semester, and that's where I started looking into solving this problem. 

Using an AWS S3 bucket with some simple scripting using the SDK would likely be a fairly clean and simple solution to code, but our office does not have, nor otherwise need an AWS account, and getting that approved for a single use such as this is not likely to happen. I wouldn't be able to just use my own AWS account and resources since this tool would likely outlive my stay in this office, whatever solution I come to needs to be transferrable and understandable by someone without my knowledge or experience.

Since we are already using Box, I have begun looking at using the Box dev tools to build a program to query our ServiceNow database for recently received devices that match a set of criteria. However, as an additional complication, our office is retiring ServiceNow at the end of the year, and moving to Workday for everything, and there is no certainty about anything, including how our inventory will be tracked or managed. Thus at this point I am left at a juncture, do I build a whole program and learn a new infrastructure just for the whole thing to potentially be scrapped in two months? What are the odds I will simply be able to swap my calls to ServiceNow's APIs to using Workday's APIs? Will this entire inventory system even exist?

    