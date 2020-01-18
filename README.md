# Rails sandboxes

- rails 4.2 + ruby 2.5 + MySQL5.7 ... container name rails42
- rails 5.0 + ruby 2.5 + MySQL5.7 ... container name rails50
- rails 5.1 + ruby 2.5 + MySQL5.7 ... container name rails51
- rails 5.2 + ruby 2.5 + MySQL5.7 ... container name rails52
- rails 6.0 + ruby 2.7 + MySQL8.0 ... container name rails60

## Usage

```sh
make start
```

```
docker container exec -it container_name sh
```

```
bundle install
bin/rails c
```
