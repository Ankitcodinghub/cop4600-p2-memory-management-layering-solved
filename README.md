# cop4600-p2-memory-management-layering-solved



**<span style='color:red'>TO GET THIS SOLUTION VISIT:</span>** https://www.ankitcodinghub.com/product/cop4600-p2-memory-management-layering-solved/

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;83880&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;COP4600  P2: Memory Management \u0026amp; Layering Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">
            
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
    
<div class="kksr-stars-active" style="width: 0px;">
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
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<h1>Overview</h1>
Due to your excellent work handling the metadata for project Sky Skink, the great Silurian overload Reptar himself has commissioned your work in designing a new custom Memory Manager application for Reptilian. This new project, deemed <strong><em>Project Repto</em></strong>, is built using functionality from various layers of the OS to avoid human corruption. For extra security, the memory manager will write a log of its state when closed. If all goes well, your manager will be deployed all throughout the great Lizard Legion.

In this project, you will implement a memory manager in C++, whose features include initializing, tracking, allocating, and deallocating sections of memory. You will integrate the memory manager into a console program that we provide. The program will provide some simple unit testing to check for correctness but will <strong>not </strong>check for memory leaks – <em>it is your responsibility to test for leaks and ensure overall correctness! </em>You must also maintain a <u>valid listing of memory holes </u>and <u>combine those holes </u>as appropriate and discussed in the class and text. You’ll then create a short video to demonstrate your code and submit the project via Canvas.

<h1>&nbsp;Structure</h1>
Modern operating systems are often built in layers with specific goals and limited privileges. Layering also facilitates the implementation of recognized standards by separating hardware and OS-specific implementations from generalized API calls. Your memory manager will make use of these standard functions so that it can be used in console applications.

The project is broken into three main parts:

<ul>
<li>Write a memory manager in C++ using basic system functionality.</li>
<li>Integrate the memory manager into the console-based testing program we provide.</li>
</ul>
<strong>Figure 1: Memory manager is instantiated from a console program.</strong>

While exact implementation may vary, <em><u>the library functions must match the signatures laid out in this document.</u></em>

<h2>&nbsp;Specification</h2>
The memory manager will incorporate the following class(es) and function(s).

<u>Memory Manager Class</u>

The Memory Manager will handle the allocation/deallocation of memory and provide details of its state. How the class keeps track of allocation/deallocation is implementation dependent and is left for the student to decide. <strong>MemoryManager.h </strong>and <strong>MemoryManager.cpp </strong>will contain declaration and definition, respectively.

<em>public </em><strong>MemoryManager</strong>(unsigned wordSize, std::function&lt;int(int, void *)&gt; allocator)

Constructor; sets native word size (in bytes, for alignment) and default allocator for finding a memory hole.

<em>public </em><strong>~MemoryManager</strong>()

Releases all memory allocated by this object <strong><em>without leaking memory</em></strong>.

<em>public </em><em>void </em><strong>initialize</strong>(size_t sizeInWords)

Instantiates block of requested size, no larger than 65536 words; cleans up previous block if applicable.

<em>public </em><em>void </em><strong>shutdown</strong>()

Releases memory block acquired during initialization, if any. This should only include memory created for long term use not those that returned such as <em>getList() </em>or <em>getBitmap() </em>as whatever is calling those should delete it instead.

<em>public </em><em>void *</em><strong>allocate</strong>(size_t sizeInBytes)

Allocates a memory using the allocator function. If no memory is available or size is invalid, returns <strong>nullptr</strong>.

<em>public </em><em>void </em><strong>free</strong>(void *address)

Frees the memory block within the memory manager so that it can be reused.

<em>public </em><em>void </em><strong>setAllocator</strong>(std::function&lt;int(int, void *)&gt; allocator)

Changes the allocation algorithm to identifying the memory hole to use for allocation.

<em>public </em><em>int </em><strong>dumpMemoryMap</strong>(char *filename)

Uses standard POSIX calls to write hole list to filename <strong><u>as text</u></strong>, returning <strong>-1 </strong>on error and <strong>0 </strong>if successful.

Format: “[START, LENGTH] – [START, LENGTH] …”, e.g., “<strong>[0, 10] – [12, 2] – [20, 6]</strong>”

<em>public </em><em>void *</em><strong>getList</strong>()

Returns an array of information (<strong><u>in decimal</u></strong>) about holes for use by the allocator function (<em>little-Endian</em>). Offset and length are in <u>words</u>. If no memory has been allocated, the function should return a <strong><em>NULL </em></strong>pointer.

Format: &nbsp;&nbsp;&nbsp;&nbsp; Example: <strong>[3, 0, 10, 12, 2, 20, 6]</strong>

<em>public </em><em>void *</em><strong>getBitmap</strong>()

Returns a bit-stream of bits in terms of an array representing whether words are used (<strong>1</strong>) or free (<strong>0</strong>). The first two bytes are the size of the bitmap (<em>little-Endian</em>); the rest is the bitmap, word-wise.

<strong><em>Note : In the following example B0, B2, and B4 are holes, B1 and B3 are allocated memory.</em></strong>

<strong><em>Hole-0&nbsp;&nbsp;&nbsp; Hole-1&nbsp;&nbsp;&nbsp; Hole-2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ┌─B4─┐&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </em></strong><strong><em>┌ B2┐&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </em></strong><strong><em>┌───B0 ──┐&nbsp;&nbsp;&nbsp;&nbsp; ┌─Size (4)─┐┌This is Bitmap in Hex┐</em></strong>

<strong><em>Example: </em></strong><strong>[0,10]-[12,2]-[20,6] </strong>[<strong>00000011111100110000000000</strong>] [<strong>0x04</strong>,<strong>0x00,0x00</strong>,<strong>0xCC</strong>,<strong>0x0F</strong>,<strong>0x00</strong>]

┕<strong><em>─B3─</em></strong>┙ ┕<strong><em>B1</em></strong><sub>┙</sub>

<strong><em>Returned Array: </em></strong>[<strong>0x04</strong>,<strong>0x00,0x00</strong>,<strong>0xCC</strong>,<strong>0x0F</strong>,<strong>0x00</strong>] or [<strong>4</strong>,<strong>0,0</strong>,<strong>204</strong>,<strong>15</strong>,<strong>0</strong>]

<em>public </em><em>unsigned </em><strong>getWordSize</strong>()

Returns the word size used for alignment.

<em>public </em><em>void *</em><strong>getMemoryStart</strong>()

Returns the byte-wise memory address of the beginning of the memory block.

<em>public </em><em>unsigned </em><strong>getMemoryLimit</strong>()

Returns the byte limit of the current memory block.

<strong>Note: The following two functions should not be part of the Memory Manager Class. </strong><u>Memory Allocation Algorithms </u><em>int </em><strong>bestFit</strong>(int sizeInWords, void *list)

Returns <strong>word offset </strong>of hole selected by the best fit memory allocation algorithm, and <strong>-1 </strong>if there is no fit.

<em>int </em><strong>worstFit</strong>(int sizeInWords, void *list)

Returns <strong>word offset </strong>of hole selected by the worst fit memory allocation algorithm, and <strong>-1 </strong>if there is no fit.

<u>Testing</u>

Your code must also compile at the command line and function with provided sample files. These sample files cover a base level functionality for the functions above. <strong><em>It is critical that you test for memory leaks! </em></strong>The code we provide will not test for this. Submissions with memory leaks will be marked <strong><u>zero </u></strong>for functionality.

<h1>&nbsp;Extra Credit</h1>
In the above implementation of MemoryManager.<strong>initialize</strong>(…), you most likely made use of the <strong>new </strong>operator to acquire your initial block of memory. Your job is to now figure out how to allocate your initial block of memory without the use of <strong>new </strong>or any stdlib functions, e.g. malloc, calloc, etc.

<h1>&nbsp;Submissions</h1>
You will submit the following at the end of this project:

<ul>
<li>Report (<strong>txt</strong>) in man format on Canvas, including link to unlisted screencast video</li>
<li>Compressed tar archive (<strong>tgz</strong>) containing source/build files for text program on Canvas</li>
</ul>
<h2>&nbsp;Report</h2>
Your report will explain how you implemented all your functions and tested them. It will describe how testing was performed, any known bugs, and why the output is correct. The report should be created using <strong>man </strong>format saved as a .txt. The report should be no more than 500 words (about two pages in man format), cover all relevant aspects of the project, and be organized and formatted professionally – <strong><em>this is not a memo!</em></strong>

<h2>&nbsp;Screencast</h2>
Students should submit a screencast (with audio) walking through each class and function. It should include showing/demoing your changes in action (no more than 5 minutes). Audio speed-up is prohibited. Video cannot have watermarks and <u>must be unlisted!</u>

<h2>&nbsp;Compressed Archive (MemoryManager.tgz)</h2>
Your compressed tar file should have the following directory/file structure:

MemoryManager.tgz

MemoryManager.tar

MemoryManager (directory) MemoryManager.h

MemoryManager.cpp

Makefile

(Other source files)

To build your program, we will execute these commands:

<strong>$ </strong><strong>tar zxvf MemoryManager.tgz</strong>

<strong>$ </strong><strong>cd MemoryManager</strong>

<strong>$ </strong><strong>make</strong>

<strong>$ </strong><strong>cd ..</strong>

To link against the library, we will execute this command:

<strong>$ </strong><strong>c++ -std=c++17 -o program_name sourcefile.c -L ./MemoryManager -lMemoryManager</strong>

Please test your functions before submission! If your code does not compile it will result in <strong><u>zero credit </u></strong>(0, none, goose-egg) for that portion of the project.

<h1>Helpful Links</h1>
You may find these resources useful as you develop and test your memory manager.

<h2>&nbsp;Development</h2>
<a href="https://www.cs.rit.edu/~ark/lectures/gc/03_00_00.html">https://www.cs.rit.edu/~ark/lectures/gc/03_00_00.html </a><a href="https://www.ibm.com/developerworks/library/pa-dalign/index.html">https://www.ibm.com/developerworks/library/pa-dalign/index.html </a><a href="https://en.cppreference.com/w/cpp/utility/functional/function">https://en.cppreference.com/w/cpp/utility/functional/function</a>

<h2>&nbsp;Testing</h2>
<a href="http://valgrind.org/">http://valgrind.org/ </a><a href="https://github.com/catchorg/Catch2">https://github.com/catchorg/Catch2</a>

&nbsp;

#include “MemoryManager/MemoryManager.h”

#include &lt;string&gt; #include &lt;cmath&gt;

#include &lt;array&gt;

#include &lt;sstream&gt;

#include &lt;fstream&gt;

#include &lt;vector&gt;

#include &lt;iostream&gt;

// test cases

unsigned int testMemoryLeaksNoShutdown(); unsigned int testSimpleFirstFit(); unsigned int testSimpleBestFit(); unsigned int testComplexBestFit(); unsigned int testNewAllocator(); unsigned int testInvalidAllocate(); unsigned int testRepeatedShutdown(); unsigned int testMaxInitialization(); unsigned int testGetters();

unsigned int testReadingUsingGetMemoryStart();

// helper functions

std::string vectorToString(const std::vector&lt;uint16_t&gt;&amp; vector);

unsigned int testGetBitmap(MemoryManager&amp; memoryManager, uint16_t correctBitmapLength, std::vector&lt;uint8_t&gt; correctBitmap); unsigned int testGetList(MemoryManager&amp; memoryManager, uint16_t correctListLength, std::vector&lt;uint16_t&gt; correctList);

unsigned int testGetWordSize(MemoryManager&amp; memoryManager, size_t correctWordSize); unsigned int testGetMemoryLimit(MemoryManager&amp; memoryManager, size_t correctMemoryLimit);

unsigned int testDumpMemoryMap(MemoryManager&amp; memoryManager, std::string fileName, std::string correctFileContents);

int hopesAndDreamsAllocator(int sizeInWords, void* list)

{

static int wordOffsetIndex = 2;

int largestWordOffsets[] = {‐1,‐1,‐1};

int largestWordOffsetsLength[] = {‐1,‐1,‐1};

uint16_t* holeList = static_cast&lt;uint16_t*&gt;(list); uint16_t holeListlength = *holeList++;

for(uint16_t i = 1; i &lt; (holeListlength) * 2; i += 2) {

if(holeList[i] &gt;= sizeInWords) {

if(holeList[i] &gt; largestWordOffsetsLength[2]) {

largestWordOffsets[0] = largestWordOffsets[1];

largestWordOffsets[1] = largestWordOffsets[2]; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;largestWordOffsets[2] = holeList[i ‐ 1];

largestWordOffsetsLength[0] = largestWordOffsetsLength[1];

largestWordOffsetsLength[1] = largestWordOffsetsLength[2];

largestWordOffsetsLength[2] = holeList[i];

}

else if(holeList[i] &gt; largestWordOffsetsLength[1]) {

largestWordOffsets[0] = largestWordOffsets[1]; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;largestWordOffsets[1] = holeList[i ‐ 1];

largestWordOffsetsLength[0] = largestWordOffsetsLength[1];

largestWordOffsetsLength[1] = holeList[i];

}

else if(holeList[i] &gt; largestWordOffsetsLength[0]) {

largestWordOffsets[0] = holeList[i ‐ 1];

largestWordOffsetsLength[0] = holeList[i]; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}

} &nbsp;&nbsp;&nbsp;&nbsp;}

int wordOffset = largestWordOffsets[wordOffsetIndex];

‐‐wordOffsetIndex;

if(wordOffsetIndex == ‐1) {

wordOffsetIndex = 2; &nbsp;&nbsp;&nbsp;&nbsp;}

return wordOffset;

}

int main() {

unsigned int maxScore = 38;

unsigned int score = 0; score += testMemoryLeaksNoShutdown(); // 0 score += testSimpleFirstFit(); // 3

std::cout &lt;&lt; “Score: ” &lt;&lt; score &lt;&lt; ” / ” &lt;&lt;&nbsp; maxScore &lt;&lt; std::endl;

score += testSimpleBestFit(); // 3

std::cout &lt;&lt; “Score: ” &lt;&lt; score &lt;&lt; ” / ” &lt;&lt;&nbsp; maxScore &lt;&lt; std::endl;

&nbsp;

score += testComplexBestFit(); // 13

std::cout &lt;&lt; “Score: ” &lt;&lt; score &lt;&lt; ” / ” &lt;&lt;&nbsp; maxScore &lt;&lt; std::endl;

&nbsp;

score += testNewAllocator(); // 7

std::cout &lt;&lt; “Score: ” &lt;&lt; score &lt;&lt; ” / ” &lt;&lt;&nbsp; maxScore &lt;&lt; std::endl;

&nbsp;

score += testInvalidAllocate(); // 1

std::cout &lt;&lt; “Score: ” &lt;&lt; score &lt;&lt; ” / ” &lt;&lt;&nbsp; maxScore &lt;&lt; std::endl;

&nbsp;

score += testRepeatedShutdown(); // 3

std::cout &lt;&lt; “Score: ” &lt;&lt; score &lt;&lt; ” / ” &lt;&lt;&nbsp; maxScore &lt;&lt; std::endl;

&nbsp;

score += testMaxInitialization(); // 1

std::cout &lt;&lt; “Score: ” &lt;&lt; score &lt;&lt; ” / ” &lt;&lt;&nbsp; maxScore &lt;&lt; std::endl;

score += testGetters(); // 2

std::cout &lt;&lt; “Score: ” &lt;&lt; score &lt;&lt; ” / ” &lt;&lt;&nbsp; maxScore &lt;&lt; std::endl;

score += 5 * testReadingUsingGetMemoryStart(); // 1 * 5

&nbsp;

std::cout &lt;&lt; “Score: ” &lt;&lt; score &lt;&lt; ” / ” &lt;&lt;&nbsp; maxScore &lt;&lt; std::endl;

}

unsigned int testMemoryLeaksNoShutdown()

{

unsigned int score = 0;

unsigned int wordSize = 8;

size_t numberOfWords = 100;

MemoryManager memoryManager(wordSize, bestFit);

memoryManager.initialize(numberOfWords); uint32_t* testArray1 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10)); uint32_t* testArray2 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10)); uint32_t* testArray3 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10)); uint32_t* testArray4 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10)); uint32_t* testArray5 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10)); memoryManager.free(testArray2);

memoryManager.free(testArray4);

memoryManager.free(testArray5);

memoryManager.free(testArray1);

memoryManager.free(testArray3);

return score;

}

unsigned int testSimpleFirstFit() {

std::cout &lt;&lt; “Test Case: First Fit 1” &lt;&lt; std::endl;

unsigned int&nbsp; wordSize = 8;

size_t numberOfWords = 26;

MemoryManager memoryManager(wordSize, bestFit);

memoryManager.initialize(numberOfWords);

std::cout &lt;&lt; “allocating and freeing memory…” &lt;&lt; std::endl;

uint64_t* testArray1 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 10));

uint64_t* testArray2 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 2));

uint64_t* testArray3 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 2));

uint64_t* testArray4 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 6));

memoryManager.free(testArray1);

memoryManager.free(testArray3);

std::vector&lt;uint8_t&gt; correctBitmap{0x00,0xCC,0x0F,0x00}; &nbsp;&nbsp;&nbsp;&nbsp;uint16_t correctBitmapLength = correctBitmap.size();

std::vector&lt;uint16_t&gt; correctList = {0, 10, 12, 2, 20, 6};

uint16_t correctListLength = correctList.size() * 2;

std::cout &lt;&lt; “Testing Memory Manager state after allocations and frees” &lt;&lt; std::endl;

unsigned int score = 0;

score += testGetBitmap(memoryManager, correctBitmapLength, correctBitmap); score += testGetList(memoryManager, correctListLength, correctList);

score += testDumpMemoryMap(memoryManager, “testSimpleFirstFit.txt”, vectorToString(correctList)); memoryManager.shutdown();

return score;

}

unsigned int testSimpleBestFit()

{

std::cout &lt;&lt; “Test Case: Best Fit 1” &lt;&lt; std::endl;

unsigned int wordSize = 8; &nbsp;&nbsp;&nbsp;&nbsp;size_t numberOfWords = 96;

MemoryManager memoryManager(8, worstFit);

memoryManager.initialize(numberOfWords);

// allocate

uint32_t* testArray1 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 4));

uint32_t* testArray2 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 4));

uint32_t* testArray3 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10));

uint32_t* testArray4 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 4)); &nbsp;&nbsp;&nbsp;&nbsp;uint32_t* testArray5 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 4));

uint32_t* testArray6 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10));

// free specific allocations to create holes

memoryManager.free(testArray3); &nbsp;&nbsp;&nbsp;&nbsp;memoryManager.free(testArray5); &nbsp;&nbsp;&nbsp;&nbsp;// change allocator

memoryManager.setAllocator(bestFit);

std::cout &lt;&lt; “allocating 4 words” &lt;&lt; std::endl;

uint32_t* testArray7 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 4));

std::vector&lt;uint8_t&gt; correctBitmap{0x0F, 0xFE, 0x03, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctList = {4,5,18,78};

uint16_t correctListLength = correctList.size() * 2; std::string correctFileContents = vectorToString(correctList); unsigned int score = 0;

std::cout &lt;&lt; “Testing Memory Manager state after allocation” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmap.size(), correctBitmap);

score += testGetList(memoryManager, correctListLength, correctList);

score += testDumpMemoryMap(memoryManager, “testSimpleBestFit.txt”, vectorToString(correctList));

memoryManager.shutdown();

return score;

}

unsigned int testComplexBestFit()

{

std::cout &lt;&lt; “Test Case: Best Fit 2” &lt;&lt; std::endl;

unsigned int wordSize = 4; &nbsp;&nbsp;&nbsp;&nbsp;size_t numberOfWords = 96;

MemoryManager memoryManager(wordSize, worstFit);

memoryManager.initialize(numberOfWords);

uint32_t* testArray1 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10));

uint32_t* testArray2 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 4));

uint32_t* testArray3 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10));

uint32_t* testArray4 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 3));

uint32_t* testArray5 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10));

uint32_t* testArray6 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 2));

uint32_t* testArray7 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10));

uint32_t* testArray8 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 1));

uint32_t* testArray9 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 10));

unsigned int score = 0;

std::vector&lt;uint8_t&gt; correctBitmapBeforeFree{0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0x0F, 0x00, 0x00, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctListBeforeFree = {60, 36};

uint16_t correctListLengthBeforeFree = correctListBeforeFree.size() * 2;

std::cout &lt;&lt; “Testing Memory Manager state after initial allocations” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmapBeforeFree.size(), correctBitmapBeforeFree); score += testGetList(memoryManager, correctListLengthBeforeFree, correctListBeforeFree);

&nbsp;

// free specific allocations to create holes

memoryManager.free(testArray2);

memoryManager.free(testArray4);

memoryManager.free(testArray6);

memoryManager.free(testArray8);

std::vector&lt;uint8_t&gt; correctBitmapAfterFree{0xFF, 0xC3, 0xFF, 0xF8, 0x9F, 0xFF, 0xFD, 0x0F, 0x00, 0x00, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctListAfterFree = {10, 4, 24, 3, 37, 2, 49, 1, 60, 36};

uint16_t correctListLengthAfterFree = correctListAfterFree.size() * 2;

std::cout &lt;&lt; “Testing Memory Manager state after freeing specific areas ” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmapAfterFree.size(), correctBitmapAfterFree);

score += testGetList(memoryManager, correctListLengthAfterFree, correctListAfterFree);

// change allocator

memoryManager.setAllocator(bestFit);

std::cout &lt;&lt; “Allocating 1 words” &lt;&lt;std::endl;

uint32_t* testArray10 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 1));

std::vector&lt;uint8_t&gt; correctBitmapAfter1{0xFF, 0xC3, 0xFF, 0xF8, 0x9F, 0xFF, 0xFF, 0x0F, 0x00, 0x00, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctListAfter1 = {10, 4, 24, 3, 37, 2, 60, 36};

uint16_t correctListLengthAfter1 = correctListAfter1.size() * 2;

std::cout &lt;&lt; “Testing Memory Manager state\n” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmapAfter1.size(), correctBitmapAfter1); &nbsp;&nbsp;&nbsp;&nbsp;score += testGetList(memoryManager, correctListLengthAfter1, correctListAfter1); std::cout &lt;&lt; “Allocating 2 words” &lt;&lt;std::endl;

uint32_t* testArray11 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 2));

std::vector&lt;uint8_t&gt; correctBitmapAfter2{0xFF, 0xC3, 0xFF, 0xF8, 0xFF, 0xFF, 0xFF, 0x0F, 0x00, 0x00, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctListAfter2 = {10, 4, 24, 3, 60, 36};

uint16_t correctListLengthAfter2 = correctListAfter2.size() * 2;

std::cout &lt;&lt; “Testing Memory Manager state\n” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmapAfter2.size(), correctBitmapAfter2);

score += testGetList(memoryManager, correctListLengthAfter2, correctListAfter2);

std::cout &lt;&lt; “Allocating 3 words” &lt;&lt;std::endl;

uint32_t* testArray12 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 3));

std::vector&lt;uint8_t&gt; correctBitmapAfter3{0xFF, 0xC3, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0x0F, 0x00, 0x00, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctListAfter3 = {10, 4, 60, 36};

uint16_t correctListLengthAfter3 = correctListAfter3.size() * 2;

std::cout &lt;&lt; “Testing Memory Manager state\n” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmapAfter3.size(), correctBitmapAfter3); &nbsp;&nbsp;&nbsp;&nbsp;score += testGetList(memoryManager, correctListLengthAfter3, correctListAfter3);

uint32_t* testArray13 = static_cast&lt;uint32_t*&gt;(memoryManager.allocate(sizeof(uint32_t) * 4));

std::cout &lt;&lt; “Allocating 4 words” &lt;&lt;std::endl;

std::vector&lt;uint8_t&gt; correctBitmapAfter4{0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0x0F, 0x00, 0x00, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctListAfter4 = {60, 36};

uint16_t correctListLengthAfter4 = correctListAfter4.size() * 2;

std::cout &lt;&lt; “Testing Memory Manager state\n” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmapAfter4.size(), correctBitmapAfter4); score += testGetList(memoryManager, correctListLengthAfter4, correctListAfter4);

score += testDumpMemoryMap(memoryManager, “testComplexBestFit.txt”, vectorToString(correctListAfter4));

memoryManager.shutdown();

return score;

}

unsigned int testNewAllocator() {

std::cout &lt;&lt; “Test Case: New allocator”; &nbsp;&nbsp;&nbsp;&nbsp;unsigned int wordSize = 8; &nbsp;&nbsp;&nbsp;&nbsp;size_t numberOfWords = 88;

MemoryManager memoryManager(wordSize, worstFit);

memoryManager.initialize(numberOfWords);

uint64_t* testArray1 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 10));

uint64_t* testArray2 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 13));

uint64_t* testArray3 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 10));

uint64_t* testArray4 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 8));

uint64_t* testArray5 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 10));

uint64_t* testArray6 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 4));

uint64_t* testArray7 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 10));

memoryManager.free(testArray2);

memoryManager.free(testArray4);

memoryManager.free(testArray6);

unsigned int score = 0;

memoryManager.setAllocator(hopesAndDreamsAllocator);

std::cout &lt;&lt; “Allocating 4 words” &lt;&lt;std::endl;

uint64_t* testArray8 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 4));

std::vector&lt;uint8_t&gt; correctBitmapAfter1{0xFF, 0x03, 0x80, 0xFF, 0x01, 0xFE, 0x87, 0xFF, 0x1F, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctListAfter1 = {10, 13, 33, 8, 51, 4, 69, 19}; &nbsp;&nbsp;&nbsp;&nbsp;uint16_t correctListLengthAfter1 = correctListAfter1.size() * 2; std::cout &lt;&lt; “Testing Memory Manager state\n” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmapAfter1.size(), correctBitmapAfter1);

score += testGetList(memoryManager, correctListLengthAfter1, correctListAfter1);

std::cout &lt;&lt; “Allocating 4 words” &lt;&lt;std::endl;

uint64_t* testArray9 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 4));

std::vector&lt;uint8_t&gt; correctBitmapAfter2{0xFF, 0x3F, 0x80, 0xFF, 0x01, 0xFE, 0x87, 0xFF, 0x1F, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctListAfter2 = {14, 9, 33, 8, 51, 4, 69, 19};

uint16_t correctListLengthAfter2 = correctListAfter2.size() * 2;

std::cout &lt;&lt; “Testing Memory Manager state\n” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmapAfter2.size(), correctBitmapAfter2);

score += testGetList(memoryManager, correctListLengthAfter2, correctListAfter2);

std::cout &lt;&lt; “Allocating 4 words” &lt;&lt;std::endl;

uint64_t* testArray10 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 4));

std::vector&lt;uint8_t&gt; correctBitmapAfter3{0xFF, 0x3F, 0x80, 0xFF, 0x1F, 0xFE, 0x87, 0xFF, 0x1F, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctListAfter3 = {14, 9, 37, 4, 51, 4, 69, 19};

uint16_t correctListLengthAfter3 = correctListAfter3.size() * 2;

std::cout &lt;&lt; “Testing Memory Manager state\n” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmapAfter3.size(), correctBitmapAfter3);

score += testGetList(memoryManager, correctListLengthAfter3, correctListAfter3);

score += testDumpMemoryMap(memoryManager, “testNewAllocator.txt”, vectorToString(correctListAfter3));

memoryManager.shutdown();

return score; }

unsigned int testInvalidAllocate() {

std::cout &lt;&lt; “Test Case: invalid allocation, over the allowed amount” &lt;&lt; std::endl; &nbsp;&nbsp;&nbsp;&nbsp;unsigned int wordSize = 2; &nbsp;&nbsp;&nbsp;&nbsp;size_t numberOfWords = 20;

MemoryManager memoryManager(wordSize, worstFit);

memoryManager.initialize(numberOfWords);

uint16_t* testArray1 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * numberOfWords));

uint16_t* testArray2 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 1));

if(testArray2 == nullptr) {

std::cout &lt;&lt; “[CORRECT]\n” &lt;&lt; std::endl;

return 1;

}

else {

std::cout &lt;&lt; “[INCORRECT]\n” &lt;&lt; std::endl;

return 0;

} }

unsigned int testRepeatedShutdown()

{

std::cout &lt;&lt; “Test Case: repeated shutdown\nGenerating Memory Manager…” &lt;&lt; std::endl; &nbsp;&nbsp;&nbsp;&nbsp;unsigned int wordSize = 2;

size_t numberOfWords1 = 10;

MemoryManager memoryManager(wordSize, worstFit);

memoryManager.initialize(numberOfWords1);

uint16_t* testArray1 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 1));

uint16_t* testArray2 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 2)); &nbsp;&nbsp;&nbsp;&nbsp;uint16_t* testArray3 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 1)); &nbsp;&nbsp;&nbsp;&nbsp;uint16_t* testArray4 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 2));

uint16_t* testArray5 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 1));

memoryManager.free(testArray1);

std::cout &lt;&lt; “shutting down Memory Manager…” &lt;&lt; std::endl; &nbsp;&nbsp;&nbsp;&nbsp;memoryManager.shutdown();

std::cout &lt;&lt; “initializing Memory Manager…” &lt;&lt; std::endl;

size_t numberOfWords2 = 20;

memoryManager.initialize(numberOfWords2);

uint16_t* testArray6 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 1));

uint16_t* testArray7 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 2));

uint16_t* testArray8 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 1));

uint16_t* testArray9 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 2));

uint16_t* testArray10 = static_cast&lt;uint16_t*&gt;(memoryManager.allocate(sizeof(uint16_t) * 1));

memoryManager.free(testArray7);

memoryManager.free(testArray8);

std::vector&lt;uint8_t&gt; correctBitmap{0x71, 0x00, 0x00};

std::vector&lt;uint16_t&gt; correctList = {1,3,7,13};

uint16_t correctListLength = correctList.size() * 2;

unsigned int score = 0;

std::cout &lt;&lt; “Testing Memory Manager state\n” &lt;&lt; std::endl;

score += testGetBitmap(memoryManager, correctBitmap.size(), correctBitmap);

score += testGetList(memoryManager, correctListLength, correctList);

score += testDumpMemoryMap(memoryManager, “testRepeatedShutdown.txt”, vectorToString(correctList));

memoryManager.shutdown();

return score;

}

unsigned int testMaxInitialization() {

std::cout &lt;&lt; “Test Case: max initialization”&nbsp; &lt;&lt; std::endl;

unsigned int wordSize = 8;

size_t numberOfWords = 65535;

MemoryManager memoryManager(wordSize, worstFit); &nbsp;&nbsp;&nbsp;&nbsp;memoryManager.initialize(numberOfWords); uint64_t* testArray1 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 32768)); uint64_t* testArray2 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 32767));

if(testArray1 &amp;&amp; testArray2) {

std::cout &lt;&lt; “[CORRECT]\n” &lt;&lt; std::endl; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return 1;

}

else {

std::cout &lt;&lt; “[INCORRECT]\n” &lt;&lt; std::endl; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return 0;

} }

unsigned int testGetters() {

// perfroms simpleFirstFit

std::cout &lt;&lt; “Test Case: testGetters, wordSize = 8, numberOfWords = 26” &lt;&lt; std::endl; &nbsp;&nbsp;&nbsp;&nbsp;unsigned int wordSize = 8; &nbsp;&nbsp;&nbsp;&nbsp;size_t numberOfWords = 26;

MemoryManager memoryManager(wordSize, bestFit);

memoryManager.initialize(numberOfWords);

uint64_t* testArray1 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 10));

uint64_t* testArray2 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 2));

uint64_t* testArray3 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 2));

uint64_t* testArray4 = static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 6));

memoryManager.free(testArray1);

memoryManager.free(testArray3);

unsigned int score = 0;

score += testGetMemoryLimit(memoryManager, wordSize * numberOfWords);

score += testGetWordSize(memoryManager, wordSize);

memoryManager.shutdown();

return score;&nbsp;&nbsp; }

unsigned int testReadingUsingGetMemoryStart()

{

std::cout &lt;&lt; “Test Case: Reading memory using GetMemoryStart” &lt;&lt; std::endl; &nbsp;&nbsp;&nbsp;&nbsp;unsigned int wordSize = 8; &nbsp;&nbsp;&nbsp;&nbsp;size_t numberOfWords = 80;

MemoryManager memoryManager(wordSize, worstFit);

memoryManager.initialize(numberOfWords);

std::vector&lt;uint64_t&gt; arrayContent{1, 12, 13, 14, 15, 2, 22, 23, 24, 25, 3, 32, 33, 34, 35, 4, 42, 43, 44, 45, 5, 52, 53, 54, 55};

std::vector&lt;uint64_t&gt;::const_iterator arrayContentItr = arrayContent.begin();

std::vector&lt;uint64_t*&gt; testArrays;

testArrays.push_back(static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 5))); &nbsp;&nbsp;&nbsp;&nbsp;testArrays.push_back(static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 5))); &nbsp;&nbsp;&nbsp;&nbsp;testArrays.push_back(static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 5))); &nbsp;&nbsp;&nbsp;&nbsp;testArrays.push_back(static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 5))); &nbsp;&nbsp;&nbsp;&nbsp;testArrays.push_back(static_cast&lt;uint64_t*&gt;(memoryManager.allocate(sizeof(uint64_t) * 5)));

&nbsp;

for(auto testArray: testArrays) {

for(uint16_t i = 0; i &lt; 5; ++i) {

testArray[i] = *arrayContentItr++;

} &nbsp;&nbsp;&nbsp;&nbsp;}

unsigned int score = 0;

arrayContentItr = arrayContent.begin();

uint64_t* MemoryManagerContents = static_cast&lt;uint64_t*&gt;(memoryManager.getMemoryStart());

for(auto content: arrayContent) {

if(content != *MemoryManagerContents++) {

std::cout &lt;&lt; “Expected: ” &lt;&lt; content &lt;&lt; std::endl;

std::cout &lt;&lt; “Got: ”&nbsp; &lt;&lt; *(MemoryManagerContents ‐ 1) &lt;&lt; std::endl;

std::cout &lt;&lt; “[INCORRECT]\n” &lt;&lt; std::endl;

return score;

} &nbsp;&nbsp;&nbsp;&nbsp;}

++score;

memoryManager.shutdown();

std::cout &lt;&lt; “[CORRECT]\n” &lt;&lt; std::endl;

return score;

}

std::string vectorToString(const std::vector&lt;uint16_t&gt;&amp; vector) {

std::string vectorString = “”;

vectorString += “[” + std::to_string(vector[0]) + “, ” + std::to_string(vector[1]);

for (int i = 2; i &lt; vector.size(); i +=2)

{

vectorString += “] ‐ [” + std::to_string(vector[i]) + “, ” + std::to_string(vector[i + 1]);

}

vectorString += “]”;

return vectorString;

}

unsigned int testGetBitmap(MemoryManager&amp; memoryManager, uint16_t correctBitmapLength, std::vector&lt;uint8_t&gt; correctBitmap)

{

unsigned int score = 0;

uint8_t* bitmap = static_cast&lt;uint8_t*&gt;(memoryManager.getBitmap()); &nbsp;&nbsp;&nbsp;&nbsp;uint8_t* bitmapEntryPoint = bitmap;

uint8_t lowerByte = *bitmap++;

uint8_t higherByte = *bitmap++;

uint16_t byteStreamLength = (higherByte &lt;&lt; 8) | lowerByte;

std::cout &lt;&lt; “Testing getBitmap” &lt;&lt; std::endl;

std::cout &lt;&lt; “Expected: ” &lt;&lt; std::endl;

std::cout &lt;&lt; “[0x” &lt;&lt; std::hex &lt;&lt; (int)correctBitmap[0];

for(uint16_t i = 1; i &lt; correctBitmap.size(); ++i) {

std::cout &lt;&lt; “, 0x” &lt;&lt; std::hex &lt;&lt; (int)correctBitmap[i]; &nbsp;&nbsp;&nbsp;&nbsp;}

std::cout &lt;&lt; “]” &lt;&lt; std::endl;

std::cout &lt;&lt; “\n”; std::cout &lt;&lt; “Got:”&nbsp; &lt;&lt; std::endl; std::cout &lt;&lt; “[0x” &lt;&lt; std::hex &lt;&lt; (int)bitmap[0]; for(uint16_t i = 1; i &lt; byteStreamLength; ++i) {

std::cout &lt;&lt; “, 0x” &lt;&lt; std::hex &lt;&lt; (int)bitmap[i];

}

std::cout &lt;&lt; “]” &lt;&lt; std::endl;

for(uint16_t i = 0; i &lt; byteStreamLength; ++i) {

if(bitmap[i] != correctBitmap[i]) {

delete [] bitmapEntryPoint;

std::cout &lt;&lt; “[INCORRECT]\n” &lt;&lt; std::endl;

return score;

} &nbsp;&nbsp;&nbsp;&nbsp;}

++score;

delete [] bitmapEntryPoint;

std::cout &lt;&lt; “[CORRECT]\n” &lt;&lt; std::endl;

return score;

}

unsigned int testGetList(MemoryManager&amp; memoryManager, uint16_t correctListLength, std::vector&lt;uint16_t&gt; correctList)

{

unsigned int score = 0;

std::cout &lt;&lt; std::dec &lt;&lt; std::endl;

uint16_t* list = static_cast&lt;uint16_t*&gt;(memoryManager.getList()); &nbsp;&nbsp;&nbsp;&nbsp;uint16_t* listEntryPoint = list;

uint16_t listLength = *list++;

uint16_t bytesPerEntry = 2;

uint16_t entriesInList = listLength * bytesPerEntry;

std::cout &lt;&lt; “Testing getList” &lt;&lt; std::endl;

std::cout &lt;&lt; “Expected: ” &lt;&lt; std::endl;

std::cout &lt;&lt; std::dec &lt;&lt; “[” &lt;&lt; correctList[0];

for(uint16_t i = 1; i &lt; correctList.size(); ++i) {

std::cout &lt;&lt;“] ‐ [” &lt;&lt; correctList[i];

}

std::cout &lt;&lt; “]” &lt;&lt; std::endl;

std::cout &lt;&lt; “\n”;

std::cout &lt;&lt; “Got:”&nbsp; &lt;&lt; std::endl; std::cout &lt;&lt; std::dec &lt;&lt; “[” &lt;&lt; list[0];

for(uint16_t i = 1; i &lt; entriesInList; ++i) { &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;std::cout &lt;&lt;“] ‐ [” &lt;&lt; list[i];

}

std::cout &lt;&lt; “]” &lt;&lt; std::endl;

for(uint16_t i = 0; i &lt; entriesInList; ++i) { &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;if(list[i] != correctList[i]) { &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;delete [] listEntryPoint;

std::cout &lt;&lt; “[INCORRECT]\n” &lt;&lt; std::endl;

return score;

} &nbsp;&nbsp;&nbsp;&nbsp;}

++score;

delete [] listEntryPoint;

std::cout &lt;&lt; “[CORRECT]\n” &lt;&lt; std::endl;

return score;

}

unsigned int testGetWordSize(MemoryManager&amp; memoryManager, size_t correctWordSize) {

std::cout &lt;&lt; “Testing getWordSize” &lt;&lt; std::endl;

std::cout &lt;&lt; “Expected: ” &lt;&lt; correctWordSize &lt;&lt; std::endl;

std::cout &lt;&lt; “Got:” &lt;&lt; memoryManager.getWordSize() &lt;&lt; std::endl;

if(memoryManager.getWordSize() == correctWordSize) {

std::cout &lt;&lt; “[CORRECT]\n” &lt;&lt; std::endl;

return 1;

}

else {

std::cout &lt;&lt; “[INCORRECT]\n” &lt;&lt; std::endl;

return 0;

} }

unsigned int testGetMemoryLimit(MemoryManager&amp; memoryManager, size_t correctMemoryLimit) {

std::cout &lt;&lt; “Testing getMemoryLimit” &lt;&lt; std::endl;

std::cout &lt;&lt; “Expected: ” &lt;&lt; correctMemoryLimit &lt;&lt; std::endl;

std::cout &lt;&lt; “Got:” &lt;&lt; memoryManager.getMemoryLimit() &lt;&lt; std::endl; if(memoryManager.getMemoryLimit() == correctMemoryLimit) {

std::cout &lt;&lt; “[CORRECT]\n” &lt;&lt; std::endl;

return 1;

}

else {

std::cout &lt;&lt; “[INCORRECT]\n” &lt;&lt; std::endl; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return 0;

} }

unsigned int testDumpMemoryMap(MemoryManager&amp; memoryManager, std::string fileName, std::string correctFileContents)

{

std::cout &lt;&lt; “Testing dumpMemoryMap” &lt;&lt; std::endl;

memoryManager.dumpMemoryMap((char*)fileName.c_str());

std::ifstream testFile(fileName); &nbsp;&nbsp;&nbsp;&nbsp;if (testFile.is_open()) { &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;std::string line;

std::getline(testFile, line);

testFile.close();

std::cout &lt;&lt; “Expected: ” &lt;&lt; correctFileContents &lt;&lt; std::endl;

std::cout &lt;&lt; “Got:” &lt;&lt; line &lt;&lt; std::endl;

if(line == correctFileContents) {

std::cout &lt;&lt; “[CORRECT]\n” &lt;&lt; std::endl;

return 1;

}

else {

std::cout &lt;&lt; “[INCORRECT]\n” &lt;&lt; std::endl;

return 0;

} &nbsp;&nbsp;&nbsp;&nbsp;}

return 0; }
