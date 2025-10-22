<script>
    export default { 
        // Add Code Here to complete the task
        // Note: DO NOT USE "eval()". In security, "eval" is considered "evil"!!!
        data() {
            return {
                operators: [ "+", "-", "*", "/", "%" ],
                x: 0,
                y: 0,
                selectedOp: "",
            }
        },
        computed: {
            result() {
                if (this.selectedOp == "+") {
                    return this.x + this.y
                } else if (this.selectedOp == "-") {
                    return this.x - this.y
                } else if (this.selectedOp == "*") {
                    return this.x * this.y
                } else if (this.selectedOp == "/" && this.y != 0) {
                    return this.x / this.y
                } else if (this.selectedOp == "%") {
                    return this.x % this.y
                } else {
                    return ""
                }
            }
        }
    }
</script>

<template>
    <p>x <input v-model.number="x"></p>
    <select v-model="selectedOp">
        <option v-for="op in operators" >{{ op }}</option>
    </select>
    <p>y <input v-model.number="y"></p>
    
    <p>---------------------</p>

    <p>= {{result}}</p>
</template>

<style scoped>
    p, input { font-family: monospace; }
    p { white-space: pre; }

</style>
