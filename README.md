- name: ChatGPT GPT-3.5 Turbo reviewer and linter
  uses: fr33d00m/chatgpt-github-actions@v2.2.0
on:
  pull_request:
    types: [opened, synchronize]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: ChatGPT code reviewer
    steps:
      - name: ChatGTP code reviewer code
        uses: fr33d00m/chatgpt-github-actions@v2-turbo
        with:
          openai_api_key: ${{ secrets.openai_api_key }}
          github_token: ${{ secrets.GITHUB_TOKEN }}
          github_pr_id: ${{ github.event.number }}
          openai_engine: "gpt-3.5-turbo" #optional
          openai_temperature: 0.2 #optional
          openai_max_tokens: 2048 #optional
