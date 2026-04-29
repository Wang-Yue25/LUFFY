# LUFFY Development Repository

> 🚧 **Development Branch** - This is the main development repository for LUFFY (Learning to Reason Under Off‑Policy Guidance)

## About LUFFY

LUFFY is a reinforcement learning framework that bridges the gap between zero-RL and imitation learning by incorporating off-policy reasoning traces into the training process. This repository contains the core implementation and development work.

## 🔧 Development Status

This repository is under active development. Many features are currently being implemented or need refactoring.

## 🚀 Quick Start

⚠️ **Note**: This development version has incomplete implementations. Many features are marked as TODO and need to be completed before production use.

```bash
# Clone the repository
git clone <repository-url>
cd LUFFY

# Install dependencies
pip install -r luffy/requirements.txt

# Note: Some functionality is incomplete - check TODO list below for details
```

## 📁 Repository Structure

```
LUFFY/
├── luffy/                 # Core framework
│   ├── deepscaler/        # Scaling utilities (⚠️ API integration needed)
│   ├── verl/              # RL training components (⚠️ Some features incomplete)
│   └── ...
├── data/                  # Training data and scripts
├── eval_scripts/          # Evaluation utilities
├── exp_scripts/           # Experiment scripts
└── README.md              # This file
```

## ⚠️ Development Notes

- This is a **development version** with incomplete implementations
- Many functions contain TODO markers indicating pending work
- API integrations (OpenAI, Gemini) are currently placeholder implementations
- FSDP and distributed training features need completion


### 🔴 High Priority TODOs

- **API Integration**: OpenAI and Gemini API implementations need completion
- **Reward System**: Parallel processing and validation for reward computation  
- **FSDP Training**: Model loading and distributed training setup
- **Data Processing**: Batch dimension operations and tensor reshaping

### 📝 Complete TODO List

- [ ] **luffy/deepscaler/utils.py:45** - Add logging for API calls and errors
- [ ] **luffy/deepscaler/utils.py:46** - Support batch processing for multiple prompts
- [ ] **luffy/deepscaler/utils.py:47** - Add timeout configuration for API calls
- [ ] **luffy/deepscaler/utils.py:107** - Implement Vertex AI initialization and authentication
- [ ] **luffy/deepscaler/utils.py:108** - Configure safety settings for content generation
- [ ] **luffy/deepscaler/utils.py:109** - Set up GenerativeModel with proper system instructions
- [ ] **luffy/deepscaler/utils.py:110** - Implement retry logic with exponential backoff
- [ ] **luffy/deepscaler/utils.py:111** - Add comprehensive error handling for API access issues
- [ ] **luffy/deepscaler/utils.py:112** - Handle rate limiting and quota management
- [ ] **luffy/deepscaler/utils.py:113** - Implement response validation and text extraction
- [ ] **luffy/deepscaler/utils.py:114** - Add support for different generation configurations
- [ ] **luffy/test.py:1590** - add smaller page sizes when https://github.com/Dao-AILab/flash-attention/pull/824 is merged
- [ ] **luffy/verl/examples/split_placement/split_monkey_patch.py:141** - make a canonical logger that supports various backend
- [ ] **luffy/verl/tests/e2e/check_results.py:21** - this function needs error handling
- [ ] **luffy/verl/tests/model/test_transformer.py:22** - (sgm): add more models for test
- [ ] **luffy/verl/tests/model/test_transformer.py:50** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformer.py:111** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:34** - (sgm): add more models for test
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:81** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/model/test_transformers_ulysses.py:159** - (sgm): we can construct the position_ids_rmpad here
- [ ] **luffy/verl/tests/ray/test_high_level_scheduling_api.py:25** - pass *args and **kwargs is bug prone and not very convincing
- [ ] **luffy/verl/tests/ray/test_worker_group_basics.py:43** - pass *args and **kwargs is bug prone and not very convincing
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:54** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:83** - it seems that manual offload is slowly than FSDP offload
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:123** - (zhangchi.usc1992): 1. support create from random initialized model. 2. Support init with FSDP directly
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:163** - (zhangchi.usc1992) remove this after we switch to fsdp2
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:199** - (zhangchi.usc1992, shengguangming) fix me. Current, auto_wrap_policy causes HFRollout to hang in Gemma
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:207** - add transformer policy
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:226** - add more optimizer args into config
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:252** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:263** - a sharding manager that do nothing?
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:391** - here, we should return all metrics
- [ ] **luffy/verl/verl/mix_src/mix_fsdp_worker.py:517** - support DCP and save sharded checkpoints
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:90** - add other ways to estimate advantages
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:168** - support each role have individual ray_worker_group_cls,
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:293** - we have to make sure the batch size is divisible by the dp size
- [ ] **luffy/verl/verl/mix_src/mix_trainer.py:599** - make a canonical logger that supports various backend
- [ ] **luffy/verl/verl/mix_src/mix_trainer_acc_rebatch.py:12** - we have to make sure the batch size is divisible by the dp size
- [ ] **luffy/verl/verl/mix_src/mix_vllm_rollout.py:40** - 
- [ ] **luffy/verl/verl/mix_src/mix_vllm_rollout.py:41** - 
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_attention.py:98** - 
- [ ] **luffy/verl/verl/models/llama/megatron/layers/parallel_decoder.py:79** - add sequence parallel operator reduce_scatter here
- [ ] **luffy/verl/verl/models/llama/megatron/modeling_llama_megatron.py:67** -  1. Add weight initialization. Here we need to be careful on TP weight init.
- [ ] **luffy/verl/verl/models/registry.py:16** - (sgm): HF may supported more than listed here, we should add more after testing
- [ ] **luffy/verl/verl/models/transformers/llama.py:218** - 
- [ ] **luffy/verl/verl/protocol.py:85** - Implement batch dimension folding for efficient processing
- [ ] **luffy/verl/verl/protocol.py:86** - Add validation for batch size divisibility
- [ ] **luffy/verl/verl/single_controller/ray/base.py:357** - create a class with customizable name
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:16** - (zhangchi.usc1992):
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:17** - 1. support pretrain from random weights
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:18** - 2. support loading HuggingFace models
- [ ] **luffy/verl/verl/trainer/fsdp_sft_trainer.py:19** - 3. support FSDP
- [ ] **luffy/verl/verl/trainer/main_ppo.py:59** - Implement reward computation for different data sources
- [ ] **luffy/verl/verl/trainer/main_ppo.py:60** - Current implementation is incomplete and needs to be finished
- [ ] **luffy/verl/verl/trainer/main_ppo.py:64** - Apply appropriate reward function based on data source
- [ ] **luffy/verl/verl/trainer/main_ppo.py:65** - Handle edge cases and error conditions
- [ ] **luffy/verl/verl/trainer/main_ppo.py:70** - Implement batch-wise reward computation
- [ ] **luffy/verl/verl/trainer/main_ppo.py:71** - Add proper error handling and validation
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:129** - add other ways to estimate advantages
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:207** - add response length
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:330** - support each role have individual ray_worker_group_cls,
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:379** - we have to make sure the batch size is divisible by the dp size
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:632** - check path
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:667** - from remote not implemented yet
- [ ] **luffy/verl/verl/trainer/ppo/ray_trainer.py:880** - make a canonical logger that supports various backend
- [ ] **luffy/verl/verl/utils/checkpoint/fsdp_checkpoint_manager.py:101** - shall we remove previous ckpt every save?
- [ ] **luffy/verl/verl/utils/checkpoint/fsdp_checkpoint_manager.py:135** - address optimizer is None
- [ ] **luffy/verl/verl/utils/hdfs_io.py:67** - (haibin.lin):
- [ ] **luffy/verl/verl/utils/hdfs_io.py:102** - (haibin.lin):
- [ ] **luffy/verl/verl/utils/megatron/tensor_parallel.py:137** - vocab_parallel_log_probs_from_logits
- [ ] **luffy/verl/verl/utils/megatron_utils.py:202** - (sgm): check how to disable megatron timers
- [ ] **luffy/verl/verl/utils/model.py:164** - we can make this faster
- [ ] **luffy/verl/verl/utils/model.py:272** - to find a better way to load mistral7b-rm lm_head
- [ ] **luffy/verl/verl/utils/torch_functional.py:162** - Technically, we only need one broadcast
- [ ] **luffy/verl/verl/utils/torch_functional.py:171** - add them back
- [ ] **luffy/verl/verl/utils/torch_functional.py:362** - add them back
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:158** - (zhangchi.usc1992): actually, this function should only return log_prob and this logic should be handled by user outside
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:225** - actually, we just need to control the sampling order.
- [ ] **luffy/verl/verl/workers/actor/megatron_actor.py:301** - we may use the new schedule instead
- [ ] **luffy/verl/verl/workers/critic/megatron_critic.py:176** - we may use the new schedule instead
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:88** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:117** - it seems that manual offload is slowly than FSDP offload
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:157** - (zhangchi.usc1992): 1. support create from random initialized model. 2. Support init with FSDP directly
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:197** - (zhangchi.usc1992) remove this after we switch to FSDP2
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:225** - (zhangchi.usc1992, shengguangming) fix me. Current, auto_wrap_policy causes HFRollout to hang in Gemma
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:233** - add transformer policy
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:252** - add more optimizer args into config
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:278** - (sgm): support FSDP hybrid shard for larger model
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:289** - a sharding manager that do nothing?
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:416** - here, we should return all metrics
- [ ] **luffy/verl/verl/workers/fsdp_workers.py:811** - (sgm): we may need to extract it to dp_reward_model.py
- [ ] **luffy/verl/verl/workers/megatron_workers.py:106** - (sgm): Currently, we only support reference model param offload
- [ ] **luffy/verl/verl/workers/megatron_workers.py:204** - add more optimizer args into config
- [ ] **luffy/verl/verl/workers/megatron_workers.py:338** - here, we should return all metrics
- [ ] **luffy/verl/verl/workers/megatron_workers.py:444** - (sgm): support critic model offload
- [ ] **luffy/verl/verl/workers/megatron_workers.py:478** - support vpp here
- [ ] **luffy/verl/verl/workers/megatron_workers.py:507** - add more optimizer args into config
- [ ] **luffy/verl/verl/workers/megatron_workers.py:667** - add more optimizer args into config
- [ ] **luffy/verl/verl/workers/megatron_workers.py:720** - reward model use itself tokenizer instead of sft tokenizer
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:145** - (sgm): check why is bfloat16
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:192** - actually, we just need to control the sampling order.
- [ ] **luffy/verl/verl/workers/reward_model/megatron/reward_model.py:233** - we may use the new schedule instead
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:16** - refactor this class
- [ ] **luffy/verl/verl/workers/rollout/hf_rollout.py:98** - filter out the seq with no answers like ds-chat
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout/vllm_rollout.py:40** - 
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout/vllm_rollout.py:41** - 
- [ ] **luffy/verl/verl/workers/rollout/vllm_rollout/vllm_rollout.py:43** - 
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_ulysses.py:49** - check how to set seed for each model
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_ulysses.py:56** - check how to set seed for each model
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:82** - offload FSDP model weights
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:113** - Current impl doesn't consider FSDP with torch micro-dp
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:122** - Current impl doesn't consider FSDP with torch micro-dp
- [ ] **luffy/verl/verl/workers/sharding_manager/fsdp_vllm.py:130** - shall we build a micro_dp group for vllm when integrating with vLLM?
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:76** - after binding to the memory buffer, we can load the checkpoint here
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:253** - (sgm): this may not be true for FSDP -> vLLM
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:273** - (zhangchi.usc1992): currently, the implementation doesn't support this
- [ ] **luffy/verl/verl/workers/sharding_manager/megatron_vllm.py:323** - (zhangchi.usc1992) We can consider copy non-tp weight to another infer buffer.

## 🤝 Contributing

1. Pick a TODO item from the list above
2. Implement the functionality
3. Test your implementation
4. Update this README when TODOs are completed