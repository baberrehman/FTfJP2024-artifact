# Artifact FTfJP 2024: Disjoint Polymorphism with Intersection and Union Types

This repository contains artifact associated with FTfJP 2024 paper.

1. `coq` folder contains the Coq formalization
2. `doc` folder contains a copy of the paper

## What does the artifact comprise?

This artifact contains the Coq formalization. There are two folders with Coq formalization:

1. `section2:` Contains formalization of section 2 from paper 
2. `section3:` Contains formalization of section 3 from paper

## Artifact Structure

The Coq formalization can be found in the folder `coq`. Description of each file in
`coq` folder is:

|  File                    |   Description                                       | Reference in paper |
| :----------------------- | :-------------------------------------------------- | :----------------- |
| coq/section2/syntax.v    | Syntax and disjointness for λu                      | Section 2          |
| coq/section2/typing.v    | Type safety proofs of λu                            | Section 2          | 
| coq/section3/syntax.v    | Syntax and disjointness for polymorphic λu          | Section 3          |
| coq/section3/typing.v    | Type safety proofs of polymorphic λu                | Section 3          |



### Correspondence of important lemmas in paper (section 2) and in artifact is:


|  Lemma in Paper  |   Coq file                 |     Lemma(s) in Coq File     |
| :--------------- | :------------------------- | :--------------------------- |
| Definition 1.1   | coq/section2/syntax.v      | DisjSpec                     |
| Lemma 2.1        | coq/section2/syntax.v      | UO_or_US                     |
| Lemma 2.2        | coq/section2/syntax.v      | Disj_sound                   |
| Lemma 2.3        | coq/section2/syntax.v      | Disj_Complete_size           |
| Lemma 2.4        | coq/section2/syntax.v      | sub_refl                     |
| Lemma 2.5        | coq/section2/syntax.v      | sub_transitivity             |
| Theorem 2.6      | coq/section2/typing.v      | preservation                 |
| Theorem 2.7      | coq/section2/typing.v      | progress                     |
| Theorem 2.8      | coq/section2/typing.v      | determinism                  |


### Correspondence of important lemmas in paper (section 3) and in artifact is:


|  Lemma in Paper  |   Coq file                 |     Lemma(s) in Coq File     |
| :--------------- | :------------------------- | :--------------------------- |
| Lemma 3.1        | coq/section3/typing.v      | sub_disjoint3                |
| Lemma 3.2        | coq/section3/typing.v      | sub_refl                     |
| Lemma 3.3        | coq/section3/typing.v      | sub_transitivity             |
| Theorem 3.4      | coq/section3/typing.v      | preservation                 |
| Theorem 3.5      | coq/section3/typing.v      | progress                     |
| Theorem 3.6      | coq/section3/typing.v      | determinism                  |
| Lemma 3.7        | coq/section3/typing.v      | typing_through_subst_te      |
| Lemma 3.8        | coq/section3/typing.v      | typing_narrowing             |
| Lemma 3.9        | coq/section3/typing.v      | typing_weakening             |
| Lemma 3.10       | coq/section3/typing.v      | UO_sub_union                 |
| Lemma 3.11       | coq/section3/typing.v      | disj_sym                     |
| Lemma 3.12       | coq/section3/typing.v      | val_check_disjoint_types     |


## How to run?

We provide two alternatives for building the artifact:

1. Docker Image
2. Build From Scratch

### 1) Docker Image

Alternatively, we also provide a dockerfile in this artifact with all the dependencies
installed. You may simply build and run the docker image using the provided dockerfile.

*Please make sure that the docker is already installed on your system to follow this track.*

1. Clone this repo using command: `git clone https://github.com/baberrehman/FTfJP2024-artifact.git`
2. Change directory to the root of the artifact: `cd FTfJP2024-artifact`
3. Build docker image: `sudo docker build -t ftfjp24disj .` (**Note that . is a part of command**)
4. Run the docker container with an interactive shell: `sudo docker run -it ftfjp24disj`
5. This will open the home directory of the artifact's docker container
6. Change directory to coq formalization inside the docker container: `cd FTfJP2024-artifact/coq/`
7. Build artifact by running the make command: `make` in `section2` and `section3` folders
8. `vim` is pre-installed in the docker container to look into the files

Note that the docker container clones the same repo in itself. Reader may directly
look into the code of this repo using their preferred editor as an easier option.

### 2) Build From Scratch

#### Dependencies

Artifact is compiled with **Coq version 8.13.2**. We recommend the same for the
sake of consistency. Detailed instructions of installing `Coq` are available
at: `https://coq.inria.fr/opam-using.html`.

Artifact also depends on an external library **TLC**. Detailed installation
instructions of TLC are available at: `https://github.com/charguer/tlc/tree/20210316`.
**Recommended TLC version is 20210316**.

#### Running the artifact

Clone the repo using command: `git clone https://github.com/baberrehman/FTfJP2024-artifact.git`

We provide a `Makefile` in `section2` and `section3` folder. Open a terminal in respective folder and
run `make` command. This command will compile all the Coq files. Reader may look into
each coq file to verify the claims using their preferred editor.

