
## Active Tasks
```tasks
path includes {{query.file.path}}
group by priority
status.type is not CANCELLED
status.type is not DONE
```

## Completed Tasks
```tasks
path includes {{query.file.path}}
status.type is DONE
```

## Cancelled Tasks
```tasks
path includes {{query.file.path}}
status.type is CANCELLED
```