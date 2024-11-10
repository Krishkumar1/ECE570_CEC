# ECE570_CEC


How to use the Code Base

Download Datasets: python scripts/download_datasets.py --tasks lift --dataset_types all --hdf5_types low_dim

Extract dataset to images: python scripts/dataset_states_to_obs.py --done_mode 0 --shaped \--dataset $BASE_DATASET_DIR/lift/$DATASET_TYPE/demo_v141.hdf5 \--output_name image_dense_v141.hdf5 --camera_names agentview robot0_eye_in_hand --camera_height 84 --camera_width 84

Reproduce RoboMimic: 

python robomimic/robomimic/scripts/train.py --config robomimic/robomimic/exps/templates/$NAME_OF_ALGORITHM --dataset $PATH_TO_EXTRACTED_DATASET

View Training Results: Use tensorboard

Train CEC:
Make changes to CEC/main/robomimic/train_config/common.yaml
python CEC/main/robomimic/train.py
