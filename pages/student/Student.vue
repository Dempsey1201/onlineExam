<template>
<el-row class="tac">
    <el-col :span="6" class="aside">
        <h5>默认颜色</h5>
        <el-menu
            ref="sideBar"
            default-active="2"
            class="el-menu-vertical-demo"
            @select="handleSelect">
            <el-menu-item index="1" router-link="/info">
                <i class="el-icon-menu"></i>
                <span slot="title">学生信息</span>
            </el-menu-item>
            <el-menu-item index="2" router-link="/notify">
                <i class="el-icon-menu"></i>
                <span slot="title">通知公告</span>
            </el-menu-item>
            <el-menu-item index="3" router-link="/examList">
                <i class="el-icon-document"></i>
                <span slot="title">课程考试</span>
            </el-menu-item>
            <el-menu-item index="4" router-link="/grade">
                <i class="el-icon-setting"></i>
                <span slot="title">成绩查询</span>
            </el-menu-item>
        </el-menu>
    </el-col>
    <el-col :span="18" class="mainPanel">
        <router-view/>
    </el-col>
</el-row>
</template>

<script>
export default {
    name: 'app',
    methods: {
        handleSelect(key, keyPath) {
            this.$router.push(this.$refs.sideBar.$children[key-1].$el.getAttribute("router-link"));
        },
    }
}
</script>

<style>
.el-row {
    min-height: 800px;
}
a {
    color: black;
    text-decoration: none;
}
.el-col {
    height: 100%;
}
.aside {
    background: #666;
}
.mainPanel {
    background: white;
}
</style>
