FROM ubuntu
RUN mkdir ./app
COPY . ./app
WORKDIR ./app/
RUN git config --global user.name Vonnebulle \
 git config --global user.email nathan@laury.org \
 git clone https://github.com/Vonnebulle/big-data.git
RUN apt update
RUN apt install python3 python3-pip git virtualenv -y
RUN virtualenv -p python3 big-datas
EXPOSE 8888
RUN /bin/bash -c "source big-datas/bin/activate"
RUN pip3 install -r requirements.txt
CMD [ "jupyter", "notebook", "--port=8888", "--ip=0.0.0.0", "--allow-root"]