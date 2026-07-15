NOVEDAD: LOGIN

Ahora la app pide iniciar sesión. La primera vez, entra a /registro y crea tu
cuenta (nombre, correo, contraseña). Las veces siguientes usa /login.

NOVEDAD: RECUPERAR CONTRASEÑA Y SEGURIDAD

Se agregó "¿Olvidaste tu contraseña?" en /login, que manda un correo con un
link para poner una contraseña nueva (válido 30 minutos). Para que funcione
necesitas 2 variables de entorno nuevas en tu ".env" (y en Render):

  MAIL_USER      -> tu cuenta de Gmail
  MAIL_PASSWORD  -> una "contraseña de aplicación" (NO tu clave normal),
                    la generas en myaccount.google.com/apppasswords
                    (requiere tener activada la verificación en 2 pasos)

También se agregó SECRET_KEY como variable de entorno propia (antes estaba
fija en el código). Ver ".env.example" para el detalle de las dos.

Si no configuras MAIL_USER/MAIL_PASSWORD la app sigue funcionando igual,
simplemente el correo de recuperación no se envía (avisa en la consola).

CONFIGURAR LA BASE DE DATOS (MySQL) — SOLO LA PRIMERA VEZ

1. Copia el archivo ".env.example" y renómbralo a ".env"
2. Rellena tus datos reales de Aiven (host, puerto, usuario, clave, nombre de la base)
3. Nunca subas el archivo ".env" a GitHub (ya está en .gitignore, no hace falta que hagas nada extra)

INSTALAR DEPENDENCIAS

pip install -r requirements.txt

EJECUTAR 

python app.py

ENTORNO VIRTUAL



MEJOR ESTO QUE FUNCIOCE DE TIRON OJALA

python -m venv .venv; Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process; .\.venv\Scripts\Activate.ps1; pip install -r requirements.txt; python app.py


EN LINUX

CREAR EL ENTORNO VIRTUAL

python3 -m venv .venv

ACTIVAR EL ENTORNO VIRTUAL

source .venv/bin/activate

INSTALAR LAS DEPENDENCIAS

pip install -r requirements.txt

EJECUTAR

python app.py

para salir de modo virtual
deactivate


