<template>
  <div class="page">
    <au-panel class="section" title="组件描述">
      <p class="paragraph">
        单选框组件
      </p>
      <!-- 组件示例 -->
      <div class="component-example">
        <au-radio
          v-model="values"
          label="Please check which kind of dances do u love"
          :radios="radios"
          :validators="validators"></au-radio>
      </div>
      <!-- 组件示例 -->
    </au-panel>
    <au-panel class="section" title="Props">
      <au-table>
        <thead>
          <tr>
            <th>字段</th>
            <th>必填</th>
            <th>类型</th>
            <th>默认</th>
            <th>可选</th>
            <th>说明</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>label</td>
            <td>
              <!-- <au-icon type="check" class="au-theme-color--success"></au-icon> -->
              <au-icon type="times"></au-icon>
            </td>
            <td>String</td>
            <td><au-icon type="minus"></au-icon></td>
            <td><au-icon type="minus"></au-icon></td>
            <td>
              提示文字
            </td>
          </tr>
          <tr>
            <td>label-width</td>
            <td>
              <!-- <au-icon type="check" class="au-theme-color--success"></au-icon> -->
              <au-icon type="times"></au-icon>
            </td>
            <td></td>
            <td><au-icon type="minus"></au-icon></td>
            <td>合法的css宽度值，仅支持px单位</td>
            <td>
              输入框前的提示文字的宽度<br>
              仅inline为true时有效
            </td>
          </tr>
          <tr>
            <td>tips</td>
            <td>
              <!-- <au-icon type="check" class="au-theme-color--success"></au-icon> -->
              <au-icon type="times"></au-icon>
            </td>
            <td>
              Array<br>
              -String
            </td>
            <td><au-icon type="minus"></au-icon></td>
            <td><au-icon type="minus"></au-icon></td>
            <td>
              需要显示的解释信息<br>
            </td>
          </tr>
          <tr>
            <td>inline</td>
            <td>
              <au-icon type="times"></au-icon>
            </td>
            <td>Boolean</td>
            <td>true</td>
            <td>
              <ol class="option-list">
                <li class="au-theme-border-color--base-8">true</li>
                <li class="au-theme-border-color--base-8">false</li>
              </ol>
            </td>
            <td>
              是否横向放置label
            </td>
          </tr>
          <tr>
            <td>list-type</td>
            <td>
              <au-icon type="times"></au-icon>
            </td>
            <td>String</td>
            <td>inline</td>
            <td>
              <ol class="option-list">
                <li class="au-theme-border-color--base-8">inline</li>
                <li class="au-theme-border-color--base-8">block</li>
              </ol>
            </td>
            <td>
              选项的布局模式，inline为横向，block为纵向
            </td>
          </tr>
          <tr>
            <td>value</td>
            <td>
              <au-icon type="check" class="au-theme-color--success"></au-icon>
            </td>
            <td>Any</td>
            <td><au-icon type="minus"></au-icon></td>
            <td><au-icon type="minus"></au-icon></td>
            <td>
              值<br>
              可以是任意类型
            </td>
          </tr>
          <tr>
            <td>radios</td>
            <td>
              <au-icon type="check" class="au-theme-color--success"></au-icon>
            </td>
            <td>
              Array<br>
              -Object
            </td>
            <td>
              <au-icon type="minus"></au-icon>
            </td>
            <td>
              <ol class="option-list">
                <li class="au-theme-border-color--base-8">text: String，选项显示的文字</li>
                <li class="au-theme-border-color--base-8">value: 任意类型，选项的值</li>
              </ol>
            </td>
            <td>
              选项配置
            </td>
          </tr>
          <tr>
            <td>disabled</td>
            <td>
              <!-- <au-icon type="check" class="au-theme-color--success"></au-icon> -->
              <au-icon type="times"></au-icon>
            </td>
            <td>Boolean</td>
            <td>false</td>
            <td>
              <ol class="option-list">
                <li class="au-theme-border-color--base-8">true</li>
                <li class="au-theme-border-color--base-8">false</li>
              </ol>
            </td>
            <td>禁用</td>
          </tr>
          <tr>
            <td>warning</td>
            <td>
              <!-- <au-icon type="check" class="au-theme-color--success"></au-icon> -->
              <au-icon type="times"></au-icon>
            </td>
            <td>Boolean</td>
            <td>false</td>
            <td>
              <ol class="option-list">
                <li class="au-theme-border-color--base-8">true</li>
                <li class="au-theme-border-color--base-8">false</li>
              </ol>
            </td>
            <td>是否显示警告样式</td>
          </tr>
          <tr>
            <td>warnings</td>
            <td>
              <!-- <au-icon type="check" class="au-theme-color--success"></au-icon> -->
              <au-icon type="times"></au-icon>
            </td>
            <td>
              Array<br>
              -String
            </td>
            <td><au-icon type="minus"></au-icon></td>
            <td><au-icon type="minus"></au-icon></td>
            <td>
              需要显示的警告信息<br>
              如果给定了需要显示的警告信息，则组件将不执行validators中提供的验证器，而只是简单显示给定的警告<br>
              不管warning选项是true还是false，只要给定了警告信息就一定会显示警告样式<br>
            </td>
          </tr>
          <tr>
            <td>validators</td>
            <td>
              <!-- <au-icon type="check" class="au-theme-color--success"></au-icon> -->
              <au-icon type="times"></au-icon>
            </td>
            <td>
              Array<br>
              -Object
            </td>
            <td><au-icon type="minus"></au-icon></td>
            <td>
              <ol class="option-list">
                <li class="au-theme-border-color--base-8">validator: Function，接受一个表示当前值的参数value</li>
                <li class="au-theme-border-color--base-8">warning: String，当验证失败时需要显示的警告信息</li>
                <li class="au-theme-border-color--base-8">async: Boolean，是否为异步验证，默认为false</li>
              </ol>
            </td>
            <td>
              验证器配置<br>
              同步验证时，验证器函数只需要返回Booean类型的验证结果即可<br>
              异步验证时，需要额外配置async为true<br>
              同时，验证器函数需要返回一个promise，并在resolve函数中传递Boolean类型的验证结果给验证器<br>
              既有同步验证，又有异步验证时，验证器首先执行同步验证<br>
              只有通过了全部的同步验证时，才会执行异步验证<br>
              不管warning选项是true还是false，只要验证未通过就一定会显示警告样式<br>
            </td>
          </tr>
        </tbody>
      </au-table>
    </au-panel>
    <au-panel class="section" title="Slots">
      <au-icon type="minus"></au-icon>
    </au-panel>
    <au-panel class="section" title="Events">
      <au-table>
        <thead>
          <tr>
            <th>名称</th>
            <th>参数</th>
            <th>说明</th>
          </tr>
        </thead>
        <tbody>
          <!-- <tr>
            <td>@input</td>
            <td>
              <ol class="option-list">
                <li class="au-theme-border-color--base-8">value</li>
                <li class="au-theme-border-color--base-8">event</li>
              </ol>
            </td>
            <td>
              输入事件<br>
              参数value表示当前值<br>
              参数event表示事件对象
            </td>
          </tr> -->
          <tr>
            <td>@change</td>
            <td>
              <ol class="option-list">
                <li class="au-theme-border-color--base-8">value</li>
              </ol>
            </td>
            <td>
              值改变事件<br>
              参数value表示当前值
            </td>
          </tr>
        </tbody>
      </au-table>
      <!-- <au-icon type="minus"></au-icon> -->
    </au-panel>
    <au-panel class="section" title="Methods">
      <au-table>
        <thead>
          <tr>
            <th>名称</th>
            <th>参数</th>
            <th>说明</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>validate()</td>
            <td>
              <au-icon type="minus"></au-icon>
            </td>
            <td>
              在给定了验证器的情况下执行验证<br>
              返回一个Promise实例<br>
              需要同时验证多个表单时请使用Promise.all()方法
            </td>
          </tr>
          <tr>
            <td>clear()</td>
            <td>
              <au-icon type="minus"></au-icon>
            </td>
            <td>清除值和警告</td>
          </tr>
        </tbody>
      </au-table>
    </au-panel>
    <au-panel class="section" title="使用示例">
      <h4 class="title-1">基础用例</h4>
      <code-h lang="html" content='
        <au-radio v-model="values" label="Please check which kind of dances do u love" :radios="radios" :validators="validators"></au-radio>
      '></code-h>
      <code-h lang="js">
        export default {
          name: 'radio-examples',
          data () {
            return {
              values: [],
              radios: [
                {
                  text: 'Breaking',
                  value: 'b'
                },
                {
                  text: 'Jazz',
                  value: 'j'
                },
                {
                  text: 'Popppin',
                  value: 'p'
                },
                {
                  text: 'Locking',
                  value: 'l'
                }
              ],
              validators: [
                {
                  validator (v) {
                    return v === 'b'
                  },
                  warning: 'If bboy then bboy forever'
                }
              ]
            }
          }
        }
      </code-h>
    </au-panel>
  </div>
</template>
<script>
export default {
  name: 'radio-examples',
  data () {
    return {
      values: [],
      radios: [
        {
          text: 'Breaking',
          value: 'b'
        },
        {
          text: 'Jazz',
          value: 'j'
        },
        {
          text: 'Popppin',
          value: 'p'
        },
        {
          text: 'Locking',
          value: 'l'
        }
      ],
      validators: [
        {
          validator (v) {
            return v === 'b'
          },
          warning: 'If bboy then bboy forever'
        }
      ]
    }
  }
}
</script>
