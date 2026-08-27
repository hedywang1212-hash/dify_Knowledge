business rule 的 when 选择after后不要更新自身，因为after会自动更新，在更新就会导致activity被记录两次。⼀般在after⾥⾯更新其他表或者抛出自定义事件。如果一点要after更新表的话记得限制条件。
