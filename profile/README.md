# PropertEase - A Unified Property Listing Manager

This organization hosts all repositories with source code for the different microservices part of the _PropertEase_ architecture.

## Running

Since our external listing services are simulated, they must be run before trying to use other components (especially Website Wrappers, which directly call their APIs).

Ensure you have the following installed:
- [docker compose](https://docs.docker.com/compose/)
- [python 3.11](https://www.python.org/)

### Running the External Services

1. clone the External Services repository

```bash
git clone git@github.com:PI-PropertEase/ExternalServices.git
```

2. (optional) create and run virtual environment

```bash
python3 -m venv venv
source venv/bin/activate
```

3. install the requirements

```bash
pip install -r requirements.txt
```

4. Run External Services - refer to the `README.md` in the [External Services](https://github.com/PI-PropertEase/ExternalServices) repository. (make sure you run all external services)

### Run the rest of the system

1. clone the control-room repository

```bash
git clone git@github.com:PI-PropertEase/control-room.git
```

2. initialize submodules

```bash
git submodule update --init --recursive
```

3. run all containerized services

```bash
docker compose up -d
```

If you want to use the keycode e-mail functionality, you must edit the `.env` file in the CalendarService repository and add the password to access the SMTP server. E-mail **joao.dourado1@ua.pt** to get that password.
