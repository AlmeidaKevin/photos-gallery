# 📸 Photo Gallery App (Ionic + Angular + Capacitor)

Aplicación móvil desarrollada con Ionic Framework que permite mostrar alertas, tomar fotografías, almacenarlas y visualizarlas dentro de la app.

---

## 🚀 Instalación del proyecto

Este proyecto fue subido sin la carpeta `node_modules` usando:

```bash
rm -rf node_modules package-lock.json
```

### 🔧 Para ejecutar el proyecto:

```bash
npm install
ionic serve
```

---

## 📱 Ejecución en dispositivo físico

Este proyecto debe probarse en un **teléfono real (NO emulador)**.

### 📲 Pasos:

```bash
ionic build
ionic cap copy
ionic cap open android
```

Luego ejecutar desde Android Studio en tu dispositivo.

---

## 🔁 Actualización de cambios

### Cambios grandes:

```bash
ionic build
ionic cap copy
```

### Cambios pequeños:

```bash
ionic cap sync
```

---

## 🔐 Permisos en Android

Ubicación del archivo:

```
android/app/src/main/AndroidManifest.xml
```

### Permisos necesarios:

```xml
<uses-permission android:name="android.permission.CAMERA" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.READ_MEDIA_IMAGES" />
```

⚠️ El sistema solicitará permisos automáticamente.

---

# 📋 FUNCIONALIDADES IMPLEMENTADAS

---

## 1️⃣ Tab 1 – Mostrar alerta

Se implementó un botón que muestra un mensaje predeterminado.

### Código:

```ts
async showAlert() {
  const alert = await this.alertController.create({
    header: 'Mensaje',
    message: 'Hola 👋 este es un mensaje predeterminado',
    buttons: ['OK'],
  });

  await alert.present();
}
```

📷 **Captura de pantalla:**


<p align="center">[TAB 1 - ALERTA]</p>


<p align="center">

  <img src="https://github.com/user-attachments/assets/0f492a2e-dc91-423c-a868-33d7139dbf98" width="45%"/>
  <img src="https://github.com/user-attachments/assets/a66a1319-aa41-4ded-b9e9-d1053036697d" width="45%"/>

</p>


---

## 2️⃣ Tab 2 – Cámara y guardado de fotos

Permite tomar fotografías y guardarlas en el dispositivo.

### 📸 Captura de foto:

```ts
const capturedPhoto = await Camera.getPhoto({
  resultType: CameraResultType.Uri,
  source: CameraSource.Camera,
  quality: 100,
  saveToGallery: true,
});
```

### 💾 Guardado con apellido:

```ts
const fileName = `Almeida_${Date.now()}.jpeg`;
```

📌 Las fotos se almacenan localmente y también en la galería del teléfono.

⚠️ Puede solicitar permisos.

📷 **Captura de pantalla:**


<p align="center">[TAB 2 - CÁMARA]</p>

<p align="center">

  <img src="https://github.com/user-attachments/assets/e43d828b-3226-4591-8554-d6325ed7f446" width="45%"/>
  <img src="https://github.com/user-attachments/assets/9925dcea-bd78-452c-94e2-0e5c7ddf60b6" width="45%"/>
  <img src="https://github.com/user-attachments/assets/0678d845-3332-4c51-b223-b24d773ec4a5" width="45%"/>
  <img src="https://github.com/user-attachments/assets/8f2bb8e2-4fa3-420f-bab8-aef3488083f5" width="45%"/>
  <img src="https://github.com/user-attachments/assets/2a551141-3297-4c3b-ac2e-ba26fc9c2d22" width="45%"/>
  <img src="https://github.com/user-attachments/assets/0af0d8be-a793-4a94-b2ff-407d1c4b4f4f" width="45%"/>
  
  


</p>

---

## 3️⃣ Tab 3 – Mostrar fotos en galería

Las imágenes tomadas se muestran en formato grid dentro del Tab 3.

📷 **Captura de pantalla:**

<p align="center">[TAB 3 - GALERÍA]</p>

<p align="center">

  <img src="https://github.com/user-attachments/assets/0f492a2e-dc91-423c-a868-33d7139dbf98" width="45%"/>
  <img src="https://github.com/user-attachments/assets/a66a1319-aa41-4ded-b9e9-d1053036697d" width="45%"/>
  <img src="https://github.com/user-attachments/assets/23c700f8-98ae-42c5-b5fa-65fa3f061d0c" width="45%"/>
  <img src="https://github.com/user-attachments/assets/25ac0fcd-b0ab-47c4-bd81-cf3ce36a38f9" width="45%"/>


</p>
---

## 📂 Ejemplo de nombre de archivo

Las imágenes se guardan con el formato:

```
Apellido_timestamp.jpeg
```

Ejemplo:

```
Almeida_1776642927623.jpeg
```

---

## 🧠 Notas importantes

* Se utiliza almacenamiento local con Preferences
* Se usa Filesystem para guardar imágenes
* Se utiliza Camera de Capacitor
* Las fotos se agregan dinámicamente a la galería

---

## 🛠️ Tecnologías utilizadas

* Ionic Framework
* Angular
* Capacitor
* TypeScript

---

## 📌 Recomendaciones

* Probar siempre en dispositivo físico
* Verificar permisos de cámara
* Ejecutar `ionic build` si hay errores tras cambios

---

## 👨‍💻 Autor

Proyecto desarrollado como práctica de desarrollo móvil con Ionic.

---

