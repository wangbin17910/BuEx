<style lang="less">
@import './styles/bit-card.less';
</style>

<template>
    <Card :padding="0">
        <div class="infor-card-con">
            <Col class="infor-card-icon-con" :style="{backgroundColor: color, color: 'white'}" span="8">
            <Row class="height-100 " type="flex" align="middle" justify="center">
                <slot>
                    <div class="bit-left">
                        <Avatar>BTC</Avatar>
                        <span class="bit-info-text">比特币</span>
                    </div>

                </slot>
            </Row>
            </Col>
            <Col span="16" class="height-100">
            <Row type="flex" align="middle" justify="center" class="height-100">
                <count-up class="infor-card-count user-created-count" :id-name="idName" :end-val="endVal" :color="color" :countSize="countSize" :countWeight="countWeight">
                    <p class="infor-intro-text" slot="intro">{{ introText }}</p>
                </count-up>
            </Row>
            </Col>
        </div>
    </Card>
</template>

<script>
import countUp from './countUp.vue'

export default {
  name: 'bitCard',
  components: {
    countUp
  },
  props: {
    idName: String,
    endVal: Number,
    color: String,
    iconType: String,
    introText: String,
    countSize: {
      type: String,
      default: '30px'
    },
    countWeight: {
      type: Number,
      default: 700
    },
    iconSize: {
      type: Number,
      default: 40
    }
  }
}
</script>

