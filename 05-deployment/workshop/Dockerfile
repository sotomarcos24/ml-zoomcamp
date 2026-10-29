FROM python:3.12-slim

WORKDIR /app

# Mismas versiones que en uv.lock (el modelo se entrenó con scikit-learn 1.9.1)
RUN pip install --no-cache-dir \
    scikit-learn==1.9.1 \
    numpy==2.5.4 \
    fastapi==0.162.0 \
    uvicorn==0.54.0

COPY predict.py model.bin ./

EXPOSE 9696

ENTRYPOINT ["uvicorn", "predict:app", "--host", "0.0.0.0", "--port", "9696"]
