### Git flow Diagrams Streaming Dev Team (3-6 peoples)

<div class="flex items-center mx-0 p-0">

```mermaid {scale: 0.1}
%%{init: { 'logLevel': 'debug', 'theme': 'default' } }%%
      gitGraph
        commit
        branch develop
        commit
        branch featureA
        checkout featureA
        commit
        commit
        commit
        commit id: "PULL REQUEST" type:HIGHLIGHT
        checkout develop
        merge featureA
        commit
        branch release
        checkout release
        commit id: "add tag (DEPLOY)" tag: "release/1.0" TYPE: HIGHLIGHT
        checkout main
        merge release
        commit  tag: "1.0" TYPE: HIGHLIGHT
        checkout develop
        merge main
        branch hotfix
        checkout hotfix
        commit tag: "1.2"
        checkout develop
        merge hotfix
        checkout main
        merge hotfix
```

</div>
