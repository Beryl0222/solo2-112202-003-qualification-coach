# 实操口述证据与上岗补训

业务资料使用虚构编号和合成叙述。文本保持来件拼写和措辞。各表是独立的来源记录。
TSV 文件采用 UTF-8，首行为列名。行首 id 是该表的稳定记录号，空格和标点属于原文，空单元格表示来件未填。
日期时间采用所在地本地时间。资料内注明为编号列表的字段用竖线分隔。

## 资料字段

- `materials/cues.tsv`。shift 是实操班次，同一 shift 下 turn 为按记录先后排列的序号。speaker 为语音转写的原记录发言人。
- `materials/rules.tsv`。valid_shifts 表示证据可使用的班次数。order_text 是培训负责人发布的口径文本。
- `materials/slots.tsv`。时间和名额由教员管理，coach 同名表示同一人。capacity 是可被同时独立观察的人数。
- `materials/roster.tsv`。shift 为生产班次，assignee 是领班原拟人员。开始记录表示人员已按原交接进入岗位。
- `materials/sessions.tsv`。rank 由实操安排方维护，越大的考核场次越新。starts 是实际开课时间，practice 是共用的工装模型。

## 运行资料检查

使用 CPython 3.11.2 和标准库。资料检查仅读取输入。

```sh
python3 pack_check.py
python3 -m unittest -v
```
