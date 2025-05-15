<div align= "center">
    <h1> MT-Bench-101 </h1>
</div>

<p align="center">
<!-- A Fine-Grained Benchmark for Evaluating Large Language Models in Multi-Turn Dialogues Models -->
[ACL 2024] MT-Bench-101: A Fine-Grained Benchmark for Evaluating Large Language Models in Multi-Turn Dialogues
</p>

<p align="center">
📃 <a href="https://arxiv.org/pdf/2402.14762" target="_blank">Paper</a> •
<!-- 🤗 <a href="https://huggingface.co" target="_blank">Data (WIP)</a> •  -->
🏆 <a href="" target="_blank">Leaderboard (WIP)</a>
</p>

## Todo

- [x] Release the research paper.
- [x] Release the evaluation code.
- [x] Release the dataset.
- [ ] Develop and launch an online leaderboard.

## 💥What's New

- **\[2024.05.28\]** Code and dataset are now available (See [Installation](https://github.com/mtbench101/mt-bench-101/edit/main/README.md#installation) for details). 🎉🎉🎉
- **\[2024.05.15\]** MT-Bench-101 has been accepted by ACL 2024 main conference. 🎉🎉🎉
- **\[2024.02.22\]** Our paper is now accessible at https://arxiv.org/abs/2402.14762. 🎉🎉🎉

## About MT-Bench-101

MT-Bench-101 is specifically designed to evaluate the finegrained abilities of LLMs in **multi-turn** dialogues. By conducting a detailed analysis of real multi-turn dialogue data, we construct a three-tier hierarchical ability taxonomy comprising **4208** turns across 1388 multi-turn dialogues in **13** distinct tasks.

## Installation

~~We integrated our MT-Bench-101 benchmark into [OpenCompass](https://github.com/open-compass/opencompass) through this [PR](https://github.com/open-compass/opencompass/pull/1215/files).~~
We integrated our MT-Bench-101 benchmark into our forked [OpenCompass](https://github.com/sefira/opencompass).
OpenCompass is a comprehensive platform for large model evaluation, which provides a unified interface for evaluating various tasks and is easy to use.

<!-- [![evaluation](./doc/imgs/compass_support.svg)]({https://hub.opencompass.org.cn/dataset-detail/MT-Bench-101}) -->

#### Create virtual env

Create virtual env for OpenCompass, see OpenCompass website if you have any questions, and clone OpenCompass code.

```bash
conda create --name opencompass python=3.10 pytorch torchvision pytorch-cuda -c nvidia -c pytorch -y
conda activate opencompass
git clone https://github.com/xingyuanbu/opencompass opencompass
cd opencompass
pip install -e .
```

#### Data Preparation

Our data has been stored in the following folder under this repo.

```bash
# Dataset folder under this repo
data/subjective/mtbench101.jsonl
```

You should copy the data file from this repo into the same path of OpenCompass.
```bash
# Download dataset from this repo and copy to OpenCompass folder
# After 'cd opencompass'
mkdir data/subjective/
cp -rf $PATH_THIS_REPO/data/subjective/mtbench101.jsonl data/subjective/
```

#### Evaluation

```bash
# run
python run.py configs/eval_subjective_mtbench101.py
# debug
python run.py configs/eval_subjective_mtbench101.py --debug
```

## Leaderboard

![image](assets/leaderboard.png)

## Citation

If you find our work helpful, feel free to give us a cite.

```
@article{bai2024mt,
  title={MT-Bench-101: A Fine-Grained Benchmark for Evaluating Large Language Models in Multi-Turn Dialogues},
  author={Bai, Ge and Liu, Jie and Bu, Xingyuan and He, Yancheng and Liu, Jiaheng and Zhou, Zhanhui and Lin, Zhuoran and Su, Wenbo and Ge, Tiezheng and Zheng, Bo and others},
  journal={arXiv preprint arXiv:2402.14762},
  year={2024}
}
```
