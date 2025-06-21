# Construcción determinística de base con media = 20 y sd = 15

nulldata 100
setobs 1 1 --time-series

# Generamos 100 valores estandarizados (media 0, sd 1)
series z = normal()

# Estandarizamos para que z tenga media 0 y sd 1 exactamente
series z_centrada = z - mean(z)
series z_esc = z_centrada / sd(z_centrada)

# Transformamos para que x tenga media 20 y sd 15 exactamente
series x = 20 + 15 * z_esc
summary x



