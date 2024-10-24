# Strip the output of iPython Notebooks when committing

1. Add filter to config
   
    `git config --global/--local filter.strip-notebook-output.clean 'jupyter nbconvert --ClearOutputPreprocessor.enabled=True --to=notebook --stdin --stdout --log-level=ERROR'`

2. Create `.gitattributes` file within the repository
3. Add the following to `.gitattributes`

     `*.ipynb filter=strip-notebook-output`
4. Add and commit `.gitattributes`
5. Ready to strip iPython Notebooks when committing
