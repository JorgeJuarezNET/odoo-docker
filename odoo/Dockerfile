# Copyright 2022 Jorge Luis Juárez M. <jorge@jorgejuarez.net>
# License AGPL-3.0 or later (http://www.gnu.org/licenses/agpl
FROM odoo:12.0
MAINTAINER Jorge Luis Juárez M. <jorge@jorgejuarez.net>
USER root

# Install gosu to scale user permissions on docker
# Install other dev tools
RUN set -eux; \
	apt-get update; \
	apt-get install -y gosu \
    python3-dev \
    python3-pip \
    python3-wheel; \
    rm -rf /var/lib/apt/lists/*; \
# verify that the binary works
	gosu nobody true


COPY ./odoo.conf /etc/odoo/

COPY ./requirements.txt /odoo/requirements.txt
RUN cd /odoo && pip3 install -r requirements.txt