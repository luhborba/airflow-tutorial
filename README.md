# Instalando Airflow na Mão

A ideia deste repositório é realizar uma instalação manual do Airflow em um ambiente Linux.

## Etapas:

1. Primeiro Passo: Prepara ambiente virtual

```bash
pyenv local 3.11.7
poetry init
poetry env use 3.11.7
poetry shell
```

2. Segundo Passo: Instalar Apache-Airflow

```bash
poetry add apache-airflow
```

3. Terceiro Passo: Realizar Configuração de Ambiente

```bash
export AIRFLOW_HOME=$("pwd")
```

4. Quarto Passo: Inicializar Airflow

```bash
airflow db init
```

5. Quinto Passo: Criar usuário Administrador

```bash
airflow users create \
          --username admin \
          --firstname FIRST_NAME \
          --lastname LAST_NAME \
          --role Admin \
          --email admin@example.org
```

6. Sexto Passo: Iniciar Serviço

```bash
airflow webserver -p 8080
```


7. Sétimo Passo: Abrir um novo terminal e ativar o Scheduler

```bash
export AIRFLOW_HOME=$("pwd")
airflow scheduler
```


PS: pode escolher a porta desejada.