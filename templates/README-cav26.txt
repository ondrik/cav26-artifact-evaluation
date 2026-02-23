CAV 2026 Artifact
=======================================
Paper title: [PAPER TITLE]

Claimed badges: Available + Functional + Reusable [remove which do not apply; note that Reusable subsumes Functional]

Justification for the badges: [no need to justify Available -- just provide the DOI link in HotCRP]

  * Functional: [give reasons why you believe that the Functional badge should be awarded (if applied for)]
    - [which claims/results of the paper are replicated by the artifact and how (you can, e.g., refer to a concrete point in FULL REVIEW below), e.g.,
       Table 1: point (1)
       Figure 1: point (2)
       Figures 2 and 3: point (3)
       Figure 4: point (4) [requires external connectivity]
       Proof of Thm. 5: point (5)
      ]
    - [which claims/results cannot be replicated and why, e.g.,
       Table 2: to reproduce the results, one needs to have access to the
                computer Holly 6000, which is not available outside our research lab
       Table 3: this table is a result of a survey among undergraduate students
                at the Institute of Happiness; the survey cannot be reproduced
                as a part of the artifact, but the raw filled in questionnaires
                are available in the directory survey/
       Fig. 6: to obtain the results, one needs to have a working installation
               of AcmeVerifier of Acme Inc.; if the reviewers possess it, they
               can reproduce the results by point (6) below.
      ]
  * Reusable: [give reasons why you believe that the Reusable badge should be awarded (if applied for)]

Requirements:

  * RAM: [FILL IN]
  * CPU cores: [FILL IN]
  * Time (smoke test): [expected time to execute the smoke test on a standard laptop (including compilation, installation, etc.)]
  * Time (full review): [expected time to execute the full review (do not include the time of reviewers reading the paper, playing with the tool on their own, etc.)]

external connectivity: [NO/YES]

  [If YES, clarify here what is being accessed and why.  If external connectivity is required for some part, please indicate.]

-------------------------------------------------------------------------------
**                                SMOKE TEST                                 **
-------------------------------------------------------------------------------

[below is an example of how to write this section; delete it and substitute
with your instructions]




-------------------------------------------------------------------------------
**                               FULL REVIEW                                 **
-------------------------------------------------------------------------------

[below is an example of how to write this section; delete it and substitute
with your instructions]

Assuming the smoke test passed, run the following command to reproduce the
results.  Running the full benchmark suite can take around 1 week on a standard
laptop, so we also provide a short version containing a selection of benchmarks
that should show the same trends as the whole suite and finishes in ~4 hours.

  cd results/

  ./run_full.sh      [to run the full version ~ runtime: 1 week]

or 

  ./run_short.sh     [to run the short version ~ runtime: 4 hours]

The commands will print out progress as their execute the benchmarks.
The output will be a file "output.csv".

(1) To obtain the results in Table 1, run the following command:

    cd results/
    ./generate_table1.sh output.csv

    and the table will be printed on the standard output

(2) To obtain the results in Figure 1, run the following command:

    cd results/
    ./generate_fig1.sh output.csv

    the figure will then be in results/fig1.svg

(3) To generate Figures 2 and 3, run the following command:

    cd results/
    ./generate_figs2_3.sh output.csv

    the figure will then be in results/fig2.png and results/fig3.pdf

(4) [this point requires external connectivity]
    To generate Figure 4, run

    cd results/
    ./generate_fig4.sh survey/data.xml

    this will access the servers of Acme Inc. to generate the figure, which will be in results/fig4.svg

(5) To certify the proof of Thm. 5., run

    rocqc thm5_proof.v
    echo "exit code = $?"

    if exit code is 0, the proof is verified

(6) [optional, this step needs a working copy of AcmeVerifier]
    To generate Figure 6, run the following command
    
    # set up a working copy of AcmeVerifier on the virtual machine
    export ACME_VER_PATH=<path to the AcmeVerifier binary>
    export ACME_VER_LICENSE_KEY=<AcmeVerifier license key>
    ./run_acme.sh output_acme.csv
    ./generate_fig5.sh output_acme.csv

    the resulting figure will be in results/fig5.gif
