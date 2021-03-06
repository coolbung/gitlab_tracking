# gitlab_tracking (Redmine 2.5.1+)

Parse webhooks gitlab and add to issue

<center>
<img src="https://raw.githubusercontent.com/alfss/gitlab_tracking/master/example.png" alt="example">
</center>

## Usage

regexp search in commit message:
```
    ((fix|ref)\s*#?[0-9]+)
```
<center>
<img src="https://raw.githubusercontent.com/alfss/gitlab_tracking/master/example2.png" alt="example">
</center>


webhook url:
```
    http://redmine[:port]/gitlab_tracking/webhook_parsing
```

settings plugin in redmine:
```
    https://redmine.site.ru/settings/plugin/gitlab_tracking
```

## Example json gitlab
```
test json:
    {"before": "19eb9b3cf78b1ae44f8d475344a5b0f4f82cfc2b", "after": "024da924becaf445b0d4d1957fadb8988324dffa", "ref": "refs/heads/tgb", "user_id": 9, "user_name": "Nikolay Ulyanov", "project_id": 1, "repository": {
        "name": "site",
        "url": "git@git.site.ru:repo_space/site.git",
        "description": "site project",
        "homepage": "http://git.site.ru/repo_space/site"
    }, "commits": [
        {
            "id": "024da924becaf445b0d4d1957fadb8988324dffa",
            "message": "Merge branch ref2 into hotfix_v34.9.3",
            "timestamp": "2014-06-20T15:56:46+04:00",
            "url": "http://git.stite.ru/repo_space/site/commit/024da924becaf445b0d4d1957fadb8988324dffa",
            "author": {
                "name": "Sergey Kravchuk",
                "email": "test@test.ru"
            }
        },
        {
            "id": "024da924becaf445b0d4d1957fadb8988324dffa",
            "message": "Merge branch fix #1 into hotfix_v34.9.3",
            "timestamp": "2014-06-20T15:56:46+04:00",
            "url": "http://git.site.ru/repo_space/site/commit/024da924becaf445b0d4d1957fadb8988324dffa",
            "author": {
                "name": "Sergey Kravchuk",
                "email": "test@test.ru"
            }
        },
        {
            "id": "024da924becaf445b0d4d1957fadb8988324dffa",
            "message": "Merge branch fixt 19342 into hotfix_v34.9.3",
            "timestamp": "2014-06-20T15:56:46+04:00",
            "url": "http://git.site.ru/repo_space/site/commit/024da924becaf445b0d4d1957fadb8988324dffa",
            "author": {
                "name": "Sergey Kravchuk",
                "email": "test@test.ru"
            }
        }
    ], "total_commits_count": 3}
```