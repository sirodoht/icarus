# icarus

```sh
curl -H 'Authorization: Bearer xxx' 'https://instances.social/api/1.0/instances/list?count=0&sort_by=active_users&sort_order=desc'  > instances-sorted.json
cat instances-sorted.json | jq '.' > instances-sorted-pretty.json
cat instances-sorted.json | jq '.instances[] | select(.up == true) | select(.dead == false) | {name, users, active_users, statuses, short_desc: .info.short_description}' | jq '[inputs]' > instances-sorted-pretty-summary-onlyup.json
```

## License

MIT
