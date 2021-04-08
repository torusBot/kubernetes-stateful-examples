Adapta wordpress.yaml a StatefullSet y comprueba si al cambiar un tema se cambia tambien en las demas instancias. 
Recuerda las limitaciones de los Statefull set, necesitan un Headless Service  creado de antemano etc.
Objetivo:
1º probar si el tema cambia creando Volumenes como en counter_sset.yaml
2º probar si se pueden crear volumenes para SSets como los creamos para deployments.
3º probar si se pueden con ese segundo estilo cambi el tema en todas las instancias