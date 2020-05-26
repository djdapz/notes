## Rollout

"Revision" is a version
- first deployment creates revision 1
- enables rollback

`kubectl rollout status deployment/<name>` -> history of deployments


- 2 deployment strategies
    1) Recreate Strategy
        - destroy all, then rebuild
    1) Rolling Update (DEFAULT)
        - one at a time

updated done with `kubectl apply -f <FILE>`

### how does it do it?
- creates empty replica set
- will add one to the new replica set and remove one from the old one
    - follows this pattern over time
    
### Rollback
`kubectl rollout undo deployment/<name>`
  