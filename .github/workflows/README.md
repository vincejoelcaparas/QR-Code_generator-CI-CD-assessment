--- Naming the Workflow
name: CICD Assessment
--- Tells the github when to run the workflow
on:
  push:
    branches:
    - main
  pull_request:
    branches:
    - main
--- creating job name build to run in latest ubuntu
jobs:
  build:
    runs-on: ubuntu-latest
--- pulls your repository code into the runner so the workflow can access it
    steps:
      - name: Checkout Code
        uses: actions/checkout@v3
--- Installs Python version 3.13 on the runner
      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.13'
--- install the dependencies needed
      - name: Install Dependencies
        run: |
          python -m pip install --upgrade pip
          python -m pip install qrcode
          python -m pip install pillow
--- test run 
      - name: Run test
        run: |
          echo "run test"
          python QR_code_generator.py "https://jlabs.team/"
--- mock deployment
      - name: Mock Deployment
        run: |
          echo "Deploying..."
          
          
        
        
    

  
