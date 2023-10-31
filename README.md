# rw-fg-custom
rw-fg repo contains a small modification of the code for rw-fg that was not working.
The code was tested with the following:
- python 2.7
- pytorch 0.3.1
- torchtext 0.6.0

The following modification was necessary to make the code work.
In TableReconstructionCriterion (https://github.com/LucaDeGrandis/rw-fg-custom/blob/main/model/onmt/modules/CopyGenerator.py) there is a slight chance that the align_view object points to columns that are nonexistent. We modified the code so that when it happens the last column is used instead.
