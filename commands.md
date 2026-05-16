python -m venv .venv
.venv\Scripts\activate

pip install pyspark findspark jupyter ipykernel pandas numpy matplotlib scikit-learn pyarrow

pip freeze > requirements.txt

python -m ipykernel install --user --name hvac-big-data --display-name "Python (HVAC Big Data)"