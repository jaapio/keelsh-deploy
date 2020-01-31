# keelsh-deploy

Deploy on kubernetes via [keel.sh] webhook

This action provides an easy interface to interact from github actions to keel.sh native webhook. The action requires a working keel setup in your cluster. Consult the docs of keel how to setup keel properly.

The example below shows how to use this action

```yml
on: [release]
name: Deploy
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: deploy
        uses: jaapio/keelsh-deploy@master
        with:
          keelBaseUrl: https://keel.yourcluster.dev:9300
          image: 'myproject/image'
          tag: ${{ github.event.tag_name }}
```


[keel.sh]: https://keel.sh
