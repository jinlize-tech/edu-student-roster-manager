# G5/G9 产品修改记录

- 产品编号：$(@{number=52; product_id=JLZ-EDU-SK-042; chinese_name=学员名册管理; english_name=Student Roster Manager; repository_name=edu-student-roster-manager; repository_url=https://github.com/jinlize-tech/edu-student-roster-manager; product_type=Skill; category_code=04; category=04 教务运营中心; description=学员名册和档案整理。; target_users=System.Object[]; core_input=学员基础信息、班型、报读课程、有效期和学校规则; main_output=名册模板、字段校验、重复/缺失清单、变更记录和隐私提示; product_risk=收集过多个人信息或名册泄露; dedup_label=需要明确差异化; dedup_note=与MT-CRM区分：只生成教务名册结构，不管理销售线索与客户跟进记录。; development_status=Planned / 待研发; license=Apache-2.0; spec_version=1.0.0; workbuddy_status=PLANNED_FOR_WORKBUDDY}.product_id)
- 产品名称：学员名册管理
- 基线：EDUCATION_BASELINE_V1.0.0
- 基线提交：$BaselineCommit
- 原版本：1.0.0
- 新版本：1.0.1

## 本次修改

1. 强化产品专属执行流程、输入核对和输出验收规则。
2. 新增 scripts/validate_input.js，实际检查必填字段、冲突、未确认数据和敏感信息。
3. 新增正常、缺失、冲突、敏感信息和非法JSON场景输入。
4. 测试升级为 T1–T7 分层并保存逐项检查结果。
5. 安装包加入 Apache-2.0 LICENSE 和 THIRD_PARTY_NOTICES.md。
6. 安装包升级为 1.0.1，加入许可证、第三方声明和输入校验脚本，保留 1.0.0 ZIP。
7. 按本产品冻结规格补充专属处理规则、输入到成果的核对矩阵和去重边界。

## 产品专属增强

- 核心任务：学员名册和档案整理。
- 主要风险：收集过多个人信息或名册泄露
- 去重边界：与MT-CRM区分：只生成教务名册结构，不管理销售线索与客户跟进记录。

- 先提取班级、教师、教室、时间、学生约束和硬性规则，再生成排程草案。
- 硬冲突不得被软约束覆盖；无法消解时列出冲突、影响和升级责任人。
- 所有变更保留原状态、目标状态、生效时间和回退方式。
- 正式课表、考勤和审批结果必须由有权限人员确认后生效。

## 运行边界

- 本地模型行为：NOT_RUNTIME_VERIFIED
- WorkBuddy平台验证：WORKBUDDY_VALIDATION_NOT_IN_SCOPE
- 本轮不执行上传、安装、审核或正式发布。
