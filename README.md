# Key advantages of using GitHub Actions for CI/CD pipelines
- **CI/CD pipeline set-up is simple**: Không cần setup gì nhiều (webhooks, hardware, ...). Chỉ cần drop một file vào trong repo đang cần setup pipeline thì nó Git sẽ nhận diện được và work.
- **Respond to any webhook on GitHub:**: Có thể setup event triggers để tự động hóa CICD Pipeline. Bao gồm PR, issues, comments, ...
- **Community-powered, reusable workflows**: Có thể tự viết một workflows và public lên Github MarketPlace. 
- **Support for any platform, any language, and any cloud**

# How to build a CI/CD pipeline with GitHub Actions
- **Be clear about what a CI/CD pipeline is and should do**: 
    + CI pipeline run khi code thay đổi, nên đảm bảo mọi thứ work ổn trước khi integrated.
    + CD pipeline là bước cuối để deploy code đã build lên production.
- **GitHub Actions takes a “choose-your-own adventure” type of approach to CI/CD**: Có thể tận dụng pre-built CI workflows có sẵn trên Github MarketPlace theo bất kỳ technology nào. Hoặc cũng có để tự build cho mình một CI workflow từ ddaauaf.

##  Step 1: Create or choose a repository, and pick a project
Có thể chọn một project có sẵn, fork bất kỳ project nào trên Github hoặc là bắt đầu từ đầu.
## Step 2: Open GitHub Actions in your repository to start building your CI/CD workflow
Chuyển sang Github Actions tab trong repo sau đó sẽ thấy một danh sách các workflow template đã có sẵn
## Step 3: Make changes to your code to trigger your CI/CD pipeline
## Step 4: Take a look at the workflow visualizer and live logs to get a full look into how your pipeline is running

## REFERENES:
https://github.blog/2022-02-02-build-ci-cd-pipeline-github-actions-four-steps/


# YAML and GitHub Actions
 - Gồm 3 thành phần: name, on, jobs
    + name: Hiển thị name của workflow, nếu không có thì sẽ lấy tên của file
    + on (required): Chỉ định event để tự động triggers workflow run.
    + jobs: Chỉ định jobs nào được run
        + job_id:
            + run_on (required): Mỗi jobs là một virtual environment 
            + steps: mỗi step là một tác vụ riêng lẻ để run commands line.

## Overall Structure:
```
name: <name of your workflow>

on: <event or list of events>
jobs:
  job_1:
    name: <name of the first job>
    runs-on: <type of machine to run the job on>
    steps:
      - name: <step 1>
        run: |
          <commands>
      - name: <step 2>
        run: |
          <commands>
  job_2:
    name: <name of the second job>
    runs-on: <type of machine to run the job on>
    steps:
      - name: <step 1>
        run: |
          <commands>
      - name: <step 2>
        run: |
          <commands>
```
## REFERENCES:
- https://hsf-training.github.io/hsf-training-cicd-github/05-understanding-yaml-and-ci/index.html=
