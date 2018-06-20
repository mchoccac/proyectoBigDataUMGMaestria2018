

#muestra una linea sed -n 39000p jsonl.sql
#limpiar lineas vasios grep . fichero > fichero2
#sed '/\"limit:\"/d' Analizar_limpiado_raw.jsonl  > Analizar_limpiado_fin.jsonl
#base  de datos 2269049   248793678 15372381571
#base de daatos 2255627
#cat *.jsonl > Analizar_limpiado_fin.json
#instalar python2.7 
#usaremos una jaula para realizar una instalacion donde nos indicara todas las depencias.

mkdir env
virtualenv env
source env/bin/activate

#instalar estos
pip install numpy
pip install pandas
pip install scikit-learn
pip install matplotlib==1.5.1
pip install scipy
pip install nltk
pip install networkx==1.11
pip install tweepy==3.3.0
pip install Pillow
pip install opencv-python
pip install seaborn
pip install shapely
pip install pysal
pip install Fiona
pip install descartes
pip install basemap
pip install textblob
pip install ggplot
pip install folium
pip install plotly
pip install arrow

#https://het.as.utexas.edu/HET/Software/PyQt/installation.html 
#Para usar la gui en python para el proyecto tenemos que compilar esto
#esto se puede realizar tanto en windows, como distribuciones basados gnu/linux
#bajar esto https://sourceforge.mirrorservice.org/p/py/pyqt/PyQt4/PyQt-4.12.1/PyQt4_gpl_x11-4.12.1.tar.gz
#bajar esto  https://kent.dl.sourceforge.net/project/pyqt/sip/sip-4.19.8/sip-4.19.8.tar.gz

#descomprimir sip <br>
#cd $VIRTUAL_ENV/include/
#rm python2.7
#cp -r /usr/include/python2.7/ .
python configure.py
make
make install

#deescomprimir pyqt4
#teclear yes para aceptar la licencia
python configure-ng.py
make
make install


# la carpeta Streamig es para descargar los datos, ahi estan todos los codigos de fuente usados, recuerda esto debe de ser en la terminal o usando el IDE Pycharm
se debe de exporta las llaves generado por twitter colocarlo dentro de las comillas, 
export TWITTER_CONSUMER_KEY=""
export TWITTER_CONSUMER_SECRET=""
export TWITTER_ACCESS_TOKEN=""
export TWITTER_ACCESS_SECRET=""
# una vez exportado los llaves 
python twitter_s.py


# Analisis aqui se encuentra los analisis que se hizo, en filename es donde debes de colocar la direccion donde esta lo que se habajado en carpeta Streamig

#muestra las estadisticas
python  Estadistica.py

#muestra el grafico para su interpretacion.
python Grafico.py
