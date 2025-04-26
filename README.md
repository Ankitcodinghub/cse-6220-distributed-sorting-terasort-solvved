# cse-6220-distributed-sorting-terasort-solvved
**TO GET THIS SOLUTION VISIT:** [CSE 6220 Distributed Sorting Terasort Solvved](https://www.ankitcodinghub.com/product/cse-6220-distributed-sorting-terasort-solvved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;89739&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSE 6220 Distributed Sorting Terasort Solvved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
In this lab, your task is to implement a distributed sorting algorithm along the lines discussed in the lesson videos. Your design should be based on the assumption that the data will *not* fit in the physical memory of any one computer in your cluster but that it *will* fit in the union of all the physical memories. This assumption makes your task slightly different from classical

[distributed disk sorting benchmarks](http://sortbenchmark.org/), but many of the same principles apply.

## Getting Started

Begin by obtaining the starter code from the github repository.

&lt;pre&gt;&lt;code&gt;

git clone –recursive https://github.gatech.edu/omscse6220/lab4.git

&lt;/code&gt;&lt;/pre&gt;

Note that this is the [GT github server](https://github.gatech.edu), so you will need to authenticate with your GT credentials.

Optionally, you may choose use a git hosting service for your code. As always, please **do not make your repository public** on Github or another git hosting service. Anyone will be able to see it. If you feel the need to use a hosting service for your project, please keep your repository private. Your GT account allows you to create free private repositories on [the GT github server](https://github.gatech.edu).

## Programming

The data type you will sorting is similar to the one used in [Hadoop’s Terasort benchmark](https://hadoop.apache.org/docs/current/api/org/apache/hadoop/examples/terasort/package-summary.html#package_description). It consists of a 10-byte key and an 88-byte value. Procedures for input/output and comparison of these records are provided for you in the **terarec.h** and **terarec.c** files. Your only task is to complete the implementation of the terasort function, which has the signature

&lt;pre&gt;&lt;code&gt;

void terasort(terarec_t *local_data, int local_len, terarec_t **sorted_data, int* sorted_counts, long* sorted_displs);

&lt;/code&gt;&lt;/pre&gt;

Here local_data is the data initially stored in memory at the calling node and local_len is the number of elements in this array. The remaining parameters are for return values. The arrays sorted_count and sorted_displs indicate the length and displacement of each node’s sorted segment within the whole. Thus, the data returned to node rank represents the sorted sequence starting at sorted_displs[rank] and has length sorted_count[rank]. The data itself is returned in *sorted_data, memory which the terasort function itself allocates.

An example of the function’s usage can be found in the **terasort_main.c**.

## Testing Your Code and Measuring Performance

Performance tests will be a large part of your evaluation. You are encouraged share your ideas and results on the Piazza forum.

An example how to check the correctness of your code locally would be:

&lt;pre&gt;&lt;code&gt;

$ make clean

$ make teragen teravalidate

$ make terasort

$ mpirun -np 4 ./teragen -c 10000

$ mpirun -np 4 ./terasort

$ mpirun -np 4 ./teravalidate

&lt;/code&gt;&lt;/pre&gt;

We’ve also included the *terametrics* utility to assist with performance testing:

&lt;pre&gt;&lt;code&gt;

$ make clean

$ make teragen terametrics

$ mpirun -np 16 ./teragen -c 10000

$ mpirun -np 16 ./terametrics -c 10

&lt;/code&gt;&lt;/pre&gt;

Two example torque jobs, *example_single.pbs* and *example_multi.pbs*, are included for running on PACE.

You can get the usage of every generated executable file (e.g. teragen, terasort, teravalidate, terametrics) by running `./tera[xx] -h`.

## Deliverables

The deliverables for this lab are as follows:

* terasort.c

Please do not make any changes to the *Makefile*. If you include any additional headers or libraries, please make sure they compile as-is on the VM, PACE and through Bonnie.

## Submitting Your Code

Once you have completed and tested your implementations, please submit using the submit.py script,

&lt;pre&gt;&lt;code&gt;

python submit.py

&lt;/code&gt;&lt;/pre&gt;

which will do a quick correctness test. You may submit as many times as you like before the deadline. At the deadline, the TA will download the code and perform some timing runs. These results along with a manual inspection of the code will determine your grade.
