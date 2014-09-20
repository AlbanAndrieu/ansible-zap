# ansible-zap

A role for installing zap.


## Actions

- Ensures that zap is installed (using `apt`)


## Usage:
```
  - name: Install zap
    hosts: zap
    user: root
  #  connection: local
    
    roles:
      - zap      
```

## License

MIT
