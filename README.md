# 🐳 email-sender-docker-compose

A personal project to learn about docker concepts and put it all in practice, using: Docker, Docker-compose, Workers, Python and HTML.

## Prepare your Setup

To run this project is only necessary to have Docker installed on your machine.

https://www.docker.com/get-started/

## Running

Clone the project and, inside the cloned folder, run:

```bash
docker-compose up -d --scale worker=X
```

being "X" the number of workers you want to initalize.

## Usage

Open your browser and access the http://localhost:80, or just http://localhost

Type the subject and message, click on "Send e-mail" and done!

## Validating

To see the results, you can type in yout prompt:

```bash
docker-compose exec db psql -U postgres -d "email_sender" -c "SELECT * FROM emails"
```

And all the e-mails sent will appear next.

## Stopping

To shutdown the services on your machine, type on prompt:

```bash
docker-compose down
```

If you want to clear the volumes, add "-v" at the final of command, like this:

```bash
docker-compose down -v
```

## Seeing logs

If you want to see the logs, execute on prompt:

```bash
docker-compose logs -f -t
```

Meaning the flags:
**-f** to keep following the logs in real time
**-t** To see the timestamp of logs

If want to learn more: https://docs.docker.com/compose/reference/logs/

#

**Being this project just a docker learning, the HTML and it flux do not so clear and usable, so every time you "send" an e-mail and you are redirected to /api page, change back the URL to http://localhost to "send" another e-mail.**
