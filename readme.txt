肿瘤诊疗容量采集与交换服务

该项目汇集多个机构提交的诊疗容量数据，按照合同版本和时间窗口校验记录，生成可追踪的容量同步结果，并把处理状态保存到本地 SQLite 数据库。演示入口读取 fixtures/demo.json，用于核对导入、冲突处理和汇总输出。

测试：python3 -m unittest discover -s tests/capacity_contracts -p 'test_*.py'
构建：python3 -m compileall -q oncology_capacity_exchange
验收：python3 -m oncology_capacity_exchange.bin.capacity_sync fixtures/demo.json --db /tmp/oncology_capacity_exchange-acceptance.sqlite3
