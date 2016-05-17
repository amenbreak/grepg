grepg
===

`grepg` (pronounced Grep G) is a ruby client for [GrepPage](https://www.greppage.com).  It allows you to access your cheat sheets without leaving the terminal.

#Installation
To install `grepg` run 

```
gem install grepg
```

#Requirements
- ruby (tested on 2.1.2)


#Usage

Enter user and topic name followed by an optional search string.

```
$ grepg --help
Usage:
  grepg -u user_name -t topic_name [-s search_term]

Options:
  -u, --user=<s>                   username
  -t, --topic=<s>                  topic
  -s, --search=<s>                 text to search
  -c, --colorize    colorize output (default: true)
  -v, --version                    Print version and exit
  -h, --help                       Show this message

Examples:
  grepg -u evidanary -t css
  greppg -u evidanary -t css -s color

Defaults:
  To set default user, create a file in ~/.grepg.yml with
  default_user: test
```


For example, to get all cheats for the `git` topic for user `kdavis`

```
$ grepg -u evidanary -t git
User: evidanary, Topic: git
push tags to remote / Github
git push --tags

remove delete tag
git tag -d v0.0.8
...

```

Search for a specific string

```
$ grepg -u kdavis -t git -s stash
User: kdavis, Topic: git, Search-Term: stash
TO apply your changes
git stash --apply
...
```

#Configuration
Setup defaults in `~/.grepg.yml`

```
user: evidanary
colorize: true
```

Now, you can do

```
$ grepg -t bootstrap
User: evidanary, Topic: bootstrap
...
```

#Development
To execute tests run ```bundle exec rake spec```. To install the gem locally, first build it using ```bundle exec rake build```. Then install the gem ```gem install pkg/grepg-0.0.1.gem```

#License
grepg is under the [MIT License](http://www.opensource.org/licenses/MIT).
