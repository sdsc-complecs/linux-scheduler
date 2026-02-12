# Example Problem: Estimate $\pi$ via Monte Carlo

To explore managing procesess and threads with the Linux scheduler, we'll need an example program to run. Here, we'll use the
[4$\pi$](https://github.com/mkandes/4pi) project, a collection of simple computer programs that estimate the value of $\pi$. 

Each program in the 4$\pi$ collection differs only in the programming language it was written in, the set of features of the
language it utilized, and/or the underlying mathematical algorithm it implemented to approximate the value of $\pi$. The aim of
the project is to explore different aspects of each programming language and their feature sets from a scientific and 
high-performance computing perspective. The first set of programs included in the project estimate the value of $\pi$ via the
Monte Carlo method. This solution is particularly useful for exploring different parallel programming models, languages, 
libraries, and APIs as it is an embarrassingly parallel (albeit inefficient) solution to the problem.

### Clone the Repository

Start by cloning the repository to your local system.

*Command*
  ```
  git clone https://github.com/mkandes/4pi.git
  ```

*Output*
```
$ git clone https://github.com/mkandes/4pi.git
Cloning into '4pi'...
remote: Enumerating objects: 19, done.
remote: Counting objects: 100% (19/19), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 19 (delta 4), reused 19 (delta 4), pack-reused 0
Unpacking objects: 100% (19/19), 5.72 KiB | 977.00 KiB/s, done.
```
