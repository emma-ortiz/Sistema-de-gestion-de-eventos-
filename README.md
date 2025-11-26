<img width="1222" height="955" alt="sistema-de-gestión-de-eventos_1" src="https://github.com/user-attachments/assets/b5e29ed8-9f1b-4812-83e0-6c5babff029d" />

```sql
evento {
    id_evento integer pk increments unique
    nombre_evento varchar(255)
    descripcion text
    fecha_inicio datetime
    fecha_fin datetime
    ubicacion varchar(255)
    tipo_evento varchar(50)
    capacidad_maxima integer
    costo_entrada decimal(10,2)
    organizador varchar(100)
    estado_evento varchar(50)
}

participante {
    id_participante integer pk increments unique
    nombre varchar(100)
    apellido varchar(100)
    email varchar(100)
    telefono varchar(20)
    fecha_registro datetime
    tipo_participante varchar(50)
    empresa varchar(100)
    pais varchar(50)
}

ticket {
    id_ticket integer pk increments unique
    id_evento integer fk
    id_participante integer fk
    fecha_compra datetime
    precio_pagado decimal(10,2)
    tipo_ticket varchar(50)
    estado_ticket varchar(50)
    metodo_pago varchar(50)
    codigo_qr varchar(255)
}

agenda_evento {
    id_sesion integer pk increments unique
    id_evento integer fk
    nombre_sesion varchar(255)
    descripcion_sesion text
    hora_inicio time
    hora_fin time
    orador varchar(100)
    sala varchar(50)
    tema varchar(100)
}

patrocinador {
    id_patrocinador integer pk increments unique
    nombre_patrocinador varchar(100)
    nivel_patrocinio varchar(50)
    contacto_persona varchar(100)
    email_contacto varchar(100)
    telefono_contacto varchar(20)
    sitio_web varchar(255)
    monto_patrocinio decimal(10,2)
}

evento_patrocinador {
    id_evento_patrocinador integer pk increments unique
    id_evento integer fk
    id_patrocinador integer fk
    fecha_inicio_acuerdo date
    fecha_fin_acuerdo date
    monto_acordado decimal(10,2)
    tipo_beneficio text
}

feedback_evento {
    id_feedback integer pk increments unique
    id_evento integer fk
    id_participante integer fk
    fecha_feedback datetime
    calificacion_general integer
    comentarios_adicionales text
    sugerencias text
    calificacion_oradores decimal(4,2)
}
```

