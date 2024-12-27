
## Active Tasks
```tasks
path includes {{query.file.folder}}
group by priority
status.type is not CANCELLED
status.type is not DONE
```

## Completed Tasks
```tasks
path includes {{query.file.folder}}
status.type is DONE
```

## Cancelled Tasks
```tasks
path includes {{query.file.folder}}
status.type is CANCELLED
```

