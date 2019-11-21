FROM rocker/shiny-verse:3.6.1
RUN R -e 'install.packages("remotes")'
COPY app.R /srv/shiny-server/
COPY DESCRIPTION /srv/shiny-server/
RUN chmod -R +r /srv/shiny-server/
RUN R -e 'remotes::install_local("/srv/shiny-server/")'
CMD ["R", "-e", "shiny::runApp('/srv/shiny-server/app.R', host='0.0.0.0', port=80)"]
EXPOSE 80
