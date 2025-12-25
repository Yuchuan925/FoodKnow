<template>
  <div class="footer-with-agreements">
    <div class="footer-content">
      <span class="footer-copyright">© 2025 江南大学 FoodKnow（食晓）</span>
      <div class="footer-links">
        <a @click="showUserAgreement = true" class="footer-link">用户协议</a>
        <a @click="showPrivacyPolicy = true" class="footer-link">隐私政策</a>
      </div>
    </div>

    <!-- 用户协议弹窗 -->
    <a-modal
      v-model:open="showUserAgreement"
      title="江南大学 FoodKnow（食晓）大模型问答系统用户协议"
      width="800px"
      :footer="null"
      class="agreement-modal"
    >
      <div class="agreement-content">
        <div class="agreement-header">
          <p><strong>版本号：</strong>v1.0</p>
          <p><strong>生效日期：</strong>2025年10月01日</p>
          <p><strong>适用范围：</strong>本协议适用于所有经授权访问本校服务器（包括 VPN、SSH 等方式）的师生及工作人员使用 FoodKnow（食晓）大模型问答系统的行为。</p>
        </div>

        <div class="agreement-section">
          <h3>一、定义</h3>
          <p>1. "本校"指江南大学及其合法授权的各单位、部门。</p>
          <p>2. "本系统"是《重点研发计划》的成果之一，并提供开源版本 Yuxi-Know（https://github.com/xerrors/Yuxi-Know），部署在本校服务器、提供智能问答、学术辅助等功能的在线系统。</p>
          <p>3. "用户"指在本校授权范围内访问、使用本系统的在校师生与工作人员。</p>
        </div>

        <div class="agreement-section">
          <h3>二、服务内容</h3>
          <p><strong>1. 核心功能</strong></p>
          <p>1) 自然语言问答：依据用户输入的问题调用大模型生成回答</p>
          <p>2) 知识检索增强：结合校内知识库或公开数据源进行逻辑推理与扩展</p>
          <p><strong>2. 使用限制</strong></p>
          <p>本系统仅限教学、科研和校内行政管理等非商业用途，禁止将系统输出内容用于商业牟利、版权侵权或违反法律法规的活动。</p>
        </div>

        <div class="agreement-section">
          <h3>三、用户权限与义务</h3>
          <p><strong>1. 合法合规使用</strong></p>
          <p>严格遵守国家法律法规、本校各项规章制度与本协议规定，不得制作或传播违法、暴力、淫秽等不良信息。</p>
          <p><strong>2. 学术诚信</strong></p>
          <p>使用系统生成的内容时应注明"本内容由无锡江南大学FoodKnow（食晓）系统生成，仅供参考"；禁止将系统输出直接用于学术论文、作业等最终提交成果。</p>
          <p><strong>3. 数据输入规范</strong></p>
          <p>严禁上传或输入国家机密、个人隐私（身份证号、银行账号、健康信息等）及其他敏感数据；因用户输入违规内容导致的后果由用户自行承担。</p>
          <p><strong>4. 账户与安全</strong></p>
          <p>采用由管理员提供的账户密码，不得共享、出租或转让个人账号；如发现安全隐患，应及时报告信息中心或系统管理员。</p>
        </div>

        <div class="agreement-section">
          <h3>四、隐私保护与数据处理</h3>
          <p><strong>1. 日志记录</strong></p>
          <p>为提升系统性能、安全及责任追溯，本系统会记录访问时间、用户ID、输入摘要与输出摘要等日志，仅限校内管理员与授权维护人员访问，不对外公开。</p>
          <p><strong>2. 数据存储</strong></p>
          <p>默认不长期保存完整会话，仅保留必要诊断与审计数据，最长保留期为365天，定期清理；如需长期保存项目数据，须另行审批。</p>
          <p><strong>3. 隐私声明</strong></p>
          <p>本系统不用于用户行为画像或商业分析，所有数据处理遵守《中华人民共和国网络安全法》及本校隐私保护细则。</p>
        </div>

        <div class="agreement-section">
          <h3>五、知识产权</h3>
          <p><strong>1. 系统软件</strong></p>
          <p>Yuxi-Know 源代码遵循其原开源许可证（参见 GitHub 仓库 LICENSE 文件），本校基于此进行的二次开发组件版权归本校所有。</p>
          <p><strong>2. 模型及输出内容</strong></p>
          <p>大模型及训练数据版权归原模型提供方所有，用户对生成内容仅享有使用权，不得声明著作权；如需商业化利用，须取得原权利方及本校授权。</p>
        </div>

        <div class="agreement-section">
          <h3>六、免责声明与责任限制</h3>
          <p><strong>1. 内容准确性</strong></p>
          <p>系统回答基于大模型算法，可能存在事实错误或偏见，仅供参考，用户须自行甄别并承担风险。</p>
          <p><strong>2. 服务可用性</strong></p>
          <p>本系统在校内网络下稳定运行，但因网络、硬件或运维等原因可能中断或延迟，本校不承担短期不可用的责任。</p>
          <p><strong>3. 间接损失</strong></p>
          <p>因使用或无法使用本系统导致的任何间接损失（如业务中断、数据丢失等），本校及系统开发团队不承担赔偿责任。</p>
        </div>

        <div class="agreement-section">
          <h3>七、协议的修改与终止</h3>
          <p><strong>1. 协议变更</strong></p>
          <p>本校可根据法律法规变化或系统迭代需要随时更新本协议，并在校园网络或系统主页公告；公告后继续使用本系统即视为接受更新后的协议。</p>
          <p><strong>2. 账号管理</strong></p>
          <p>本校有权在用户严重违反本协议时暂停或注销其访问权限，并保留追究责任的权利，无需另行通知。</p>
        </div>

        <div class="agreement-section">
          <h3>八、争议解决与适用法律</h3>
          <p><strong>1. 法律适用</strong></p>
          <p>本协议的订立、执行与解释均适用中华人民共和国法律法规。</p>
          <p><strong>2. 争议解决</strong></p>
          <p>双方如发生争议，应首先友好协商；协商不成时，可向本校所在地人民法院提起诉讼。</p>
        </div>

        <div class="agreement-section">
          <h3>附：联系方式</h3>
          <p>系统维护邮箱：wenjie.zhang@stu.jiangnan.edu.cn</p>
          <p style="margin-top: 20px;"><strong>本协议由江南大学负责制定与解释，最终解释权归江南大学所有。</strong></p>
        </div>
      </div>
    </a-modal>

    <!-- 隐私政策弹窗 -->
    <a-modal
      v-model:open="showPrivacyPolicy"
      title="江南大学 FoodKnow（食晓）大模型问答系统隐私协议"
      width="800px"
      :footer="null"
      class="agreement-modal"
    >
      <div class="agreement-content">
        <div class="agreement-header">
          <p><strong>版本号：</strong>v1.0</p>
          <p><strong>生效日期：</strong>2025年10月01日</p>
          <p><strong>适用范围：</strong>适用于在无锡江南大学校内网络或经授权访问本校服务器使用 FoodKnow（食晓）大模型问答系统的所有用户。</p>
        </div>

        <div class="agreement-section">
          <h3>一、信息收集</h3>
          <p><strong>1. 用户输入内容</strong></p>
          <p>系统在用户使用过程中会接收并处理用户输入的文本，包括问题、指令及反馈等。</p>
          <p><strong>2. 系统日志</strong></p>
          <p>为保证系统安全与性能优化，系统会自动记录访问时间、用户ID（或匿名ID）、请求类型与响应摘要等日志信息。</p>
          <p><strong>3. 技术数据</strong></p>
          <p>系统可能收集与存储访问设备的操作系统版本、浏览器类型、IP地址（可用VPN时可能为VPN节点IP）及使用时长等非个人可识别技术信息。</p>
        </div>

        <div class="agreement-section">
          <h3>二、信息使用</h3>
          <p><strong>1. 服务提供</strong></p>
          <p>用户输入的内容用于大模型推理与知识检索，以生成答案与服务功能。</p>
          <p><strong>2. 性能优化</strong></p>
          <p>日志数据可用于系统性能分析、故障排查与模型迭代改进。</p>
          <p><strong>3. 安全审计</strong></p>
          <p>存储日志可用于安全事件追踪与防范滥用、攻击行为。</p>
        </div>

        <div class="agreement-section">
          <h3>三、信息存储与保留</h3>
          <p><strong>1. 存储位置</strong></p>
          <p>所有数据保存在无锡江南大学校内服务器，受校园网络及信息中心管理制度保护，不涉及第三方云平台。</p>
          <p><strong>2. 保留期限</strong></p>
          <p>完整会话记录最长保留30天，之后自动清理。技术日志及审计日志最长保留90天，后续定期归档或删除。</p>
          <p><strong>3. 数据备份</strong></p>
          <p>为防止意外丢失，关键信息将进行定期备份，备份数据同样遵守上述保留与清理策略。</p>
        </div>

        <div class="agreement-section">
          <h3>四、信息共享与披露</h3>
          <p><strong>1. 校内人员</strong></p>
          <p>除非法律法规或校内管理规定另有要求，仅限本校信息中心与系统维护团队访问日志与技术数据。</p>
          <p><strong>2. 第三方机构</strong></p>
          <p>不向任何第三方出售、交换或以其他方式共享用户数据。法律法规强制要求时，将在符合法律程序的前提下配合政府部门或司法机构。</p>
          <p><strong>3. 学术研究</strong></p>
          <p>若需将匿名聚合数据用于学术研究或论文发表，需经信息中心审批并去标识化处理。</p>
        </div>

        <div class="agreement-section">
          <h3>五、用户权利</h3>
          <p><strong>1. 查询与更正</strong></p>
          <p>用户可联系信息中心查询或更正其提供的个人信息或输入内容摘要。</p>
          <p><strong>2. 删除请求</strong></p>
          <p>用户可申请删除其在系统中产生的会话记录，由信息中心核实后在合理期限内处理。</p>
          <p><strong>3. 权利行使</strong></p>
          <p>如对本隐私协议或数据处理方式有异议，可通过指定联系方式提出书面申请或投诉。</p>
        </div>

        <div class="agreement-section">
          <h3>六、安全措施</h3>
          <p><strong>1. 访问控制</strong></p>
          <p>系统部署在校内受限网络，仅授权账户可访问，采用身份认证与权限管理。</p>
          <p><strong>2. 数据加密</strong></p>
          <p>存储敏感日志及备份文件时采用校园内网加密存储方案，传输过程中采用内网加密协议。</p>
          <p><strong>3. 安全审计</strong></p>
          <p>定期进行安全评估与渗透测试，及时修补系统漏洞与更新模型。</p>
        </div>

        <div class="agreement-section">
          <h3>七、协议更新</h3>
          <p>本校有权根据法律法规变化或系统迭代需要，随时修订本隐私协议。修订内容在校园网络或系统主页公告后生效，公告后继续使用系统视为接受更新。</p>
        </div>


        <div class="agreement-section">
          <h3>附：联系方式</h3>
          <p>系统维护邮箱：wenjie.zhang@stu.jiangnan.edu.cn</p>
          <p style="margin-top: 20px;"><strong>本协议由江南大学负责制定与解释，最终解释权归江南大学所有。</strong></p>
        </div>
      </div>
    </a-modal>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// 控制弹窗显示状态
const showUserAgreement = ref(false);
const showPrivacyPolicy = ref(false);
</script>

<style lang="less" scoped>
.footer-with-agreements {
  margin-top: 16px;
  padding-top: 16px;
  border-top: 1px solid var(--gray-150);
}

.footer-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  font-size: 13px;
}

.footer-copyright {
  color: var(--gray-600);
  font-weight: 500;
}

.footer-links {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 16px;
}

.footer-link {
  color: var(--gray-600);
  cursor: pointer;
  text-decoration: none;
  transition: color 0.2s ease;

  &:hover {
    color: var(--main-color);
  }
}

.agreement-modal {
  :deep(.ant-modal-body) {
    max-height: 70vh;
    overflow-y: auto;
  }
}

.agreement-content {
  line-height: 1.6;
}

.agreement-header {
  background-color: var(--gray-50);
  padding: 16px;
  border-radius: 4px;
  margin: 20px 0;
  border-left: 4px solid var(--main-color);

  p {
    margin: 4px 0;
    font-size: 14px;
  }
}

.agreement-section {
  margin-bottom: 24px;

  h3 {
    color: var(--main-color);
    font-size: 18px;
    font-weight: 600;
    margin-bottom: 12px;
    border-bottom: 2px solid var(--main-100);
    padding-bottom: 6px;
  }

  p {
    margin: 8px 0;
    font-size: 14px;
    color: var(--gray-700);
    text-align: justify;

    strong {
      color: var(--gray-800);
    }
  }
}
</style>