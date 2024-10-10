if: success() || failure() || cancelled()
ej: if: steps.id_name.outcome == 'success'

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: checkout
        id: checkout
        uses: actions/checkout@v3

      - name: ls
        if: steps.id_name.outcome == 'success'
        run: ls -la