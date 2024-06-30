# sb-microservices

        livenessProbe:
          {{- toYaml .Values.tempo.livenessProbe | nindent 12 }}
        readinessProbe:
          {{- toYaml .Values.tempo.readinessProbe | nindent 12 }}


  livenessProbe:
    httpGet:
      path: /ready
      port: 3100
    initialDelaySeconds: 10
    periodSeconds: 10
    timeoutSeconds: 5
    failureThreshold: 3
    successThreshold: 1

  readinessProbe:
    httpGet:
      path: /ready
      port: 3100
    initialDelaySeconds: 10
    periodSeconds: 10
    timeoutSeconds: 5
    failureThreshold: 3
    successThreshold: 1