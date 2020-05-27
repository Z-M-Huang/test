```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    name: Test
    steps:
    - uses: actions/checkout@v2
    - name: Test Get Commit
      run: echo "::set-env name=msg::abc" #$(git log -1 HEAD --pretty=format:%s)
    - name: Echo Variable
      run: echo "This is evar ${msg}"
    - name: okay... I am so good
      env:
        test: ${{ env.msg }}
      run: echo "${test}"
```