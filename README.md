# 1. Creamos la estructura del nuevo repositorio
mkdir -p ~/Proyectos_GitHub/avr-rtc-alarm/{src,docs}

# 2. Movemos los .c y .h a src
find /tmp/tp3_temp/ -name "*.c" -exec mv {} ~/Proyectos_GitHub/avr-rtc-alarm/src/ \;
find /tmp/tp3_temp/ -name "*.h" -exec mv {} ~/Proyectos_GitHub/avr-rtc-alarm/src/ \;

# 3. Movemos el archivo de simulación de Proteus a docs
find /tmp/tp3_temp/ -name "New Project.pdsprj" -exec mv {} ~/Proyectos_GitHub/avr-rtc-alarm/docs/ \;

# 4. Limpiamos la carpeta temporal
rm -rf /tmp/tp3_temp/

# 5. Entramos al nuevo repo
cd ~/Proyectos_GitHub/avr-rtc-alarm/
