1.GVHMR(video(*.mp4)-> *.pkl):

  python tools/demo/demo.py --video=docs/example_video/tennis.mp4 -s
  

2.GMR(*.pkl->*.csv):

  python scripts/gvhmr_to_robot.py --gvhmr_pred_file <path_to_hmr4d_results.pt> --robot unitree_g1 --record_video

3.mimic(*.csv->*.npz):
  python ./scripts/mimic/csv_to_npz.py --input_file /home/hello/env_isaacsim51/unitree_rl_lab/source/unitree_rl_lab/unitree_rl_lab/tasks/mimic/robots/g1_29dof/tennis/tennis.csv --input_fps 60 --output_name /home/hello/env_isaacsim51/unitree_rl_lab/source/unitree_rl_lab/unitree_rl_lab/tasks/mimic/robots/g1_29dof/tennis/tennis --headless

4.rl_lab(train *.npz)
  ./unitree_rl_lab.sh -t --task Unitree-G1-29dof-Mimic-tennis --max_iterations 50000
