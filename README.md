## coco-analyze Repository
This repository contains the code release from the paper [***Benchmarking and Error Diagnosis in Multi-Instance Pose Estimation***](http://www.vision.caltech.edu/~mronchi/projects/PoseErrorDiagnosis).

### Important Content:
 - `pycocotools/COCOanalyze.py`: wrapper of the COCOeval class for multi-instance keypoint estimation error analysis.
 - `COCOanalyze_demo.ipynb`: ipython notebook showing how to use COCOanalyze as a standalone class.
 - `analysisAPI`: API using COCOanalyze for an extended analysis.
 - `run_analysis.py`: script generating a pdf summary of the extended analysis.

### Usage
To run the extended multi-instance keypoint estimation error analysis: update the paths of the detections and annotations and execute the command line.

    [annFile]  -> ./annotations/keypoints_val2014.json
    [dtsFile]  -> ./detections/fakekeypoints100_keypoints_val2014_results.json
    [saveDir]  -> ./results/fakekeypoints100
    [teamName] -> fakekeypoints100
    [version]  -> 1.0
    $ python run_analysis.py [annFile] [dtsFile] [saveDir] [teamName] [version]

### Results
 - A summary file called `[teamName]_performance_report.tex` will be created once the analysis is complete.
 - All the generated plots are stored using `[saveDir]` as the base directory.
 - Additional *std_output* information regarding the analysis can be found in the text files named `std_out.txt`.

### Notes:
 - The [`./pycocotools/COCOeval`](https://github.com/matteorr/coco-analyze/blob/release/pycocotools/cocoeval.py) class contained in this repository is a modified version of the original [mscoco COCOeval class](https://github.com/pdollar/coco/blob/master/PythonAPI/pycocotools/cocoeval.py).
 - The duration of the full analysis depends on the number of detections and size of the ground-truth split.
 - You can update `run_analysis.py` to run the analysis only for specific types of error.
