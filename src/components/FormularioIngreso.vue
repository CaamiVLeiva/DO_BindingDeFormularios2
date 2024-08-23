<template>
    <div class="form-container bg-dark text-white p-4 rounded">
        <form>
            <div class="mb-3">
                <label for="titulo" class="form-label">Título</label>
                <input id="titulo" class="form-control" type="text" v-model="localFormData.titulo" />
            </div>
            <div class="mb-3">
                <label for="emoji" class="form-label">Emoji</label>
                <select id="emoji" class="form-select" v-model="localFormData.emoji">
                    <option value="👩‍💻">👩‍💻</option>
                    <option value="😎">😎</option>
                    <option value="😢">😢</option>
                </select>
            </div>
            <div class="mb-3">
                <div class="d-flex flex-wrap">
                    <label class="form-label me-3">Apreciación:</label>
                    <div class="me-3 mb-2">
                        <input id="apreciacion-regular" type="radio" v-model="localFormData.apreciacion" value="Regular" />
                        <label for="apreciacion-regular" class="ms-2">Regular</label>
                    </div>
                    <div class="me-3 mb-2">
                        <input id="apreciacion-bien" type="radio" v-model="localFormData.apreciacion" value="Bien" />
                        <label for="apreciacion-bien" class="ms-2">Bien</label>
                    </div>
                    <div class="me-3 mb-2">
                        <input id="apreciacion-muy-bien" type="radio" v-model="localFormData.apreciacion" value="Muy Bien" />
                        <label for="apreciacion-muy-bien" class="ms-2">Muy Bien</label>
                    </div>
                    <div class="mb-2">
                        <input id="apreciacion-increible" type="radio" v-model="localFormData.apreciacion" value="Increíble" />
                        <label for="apreciacion-increible" class="ms-2">Increíble</label>
                    </div>
                </div>
            </div>
            <div class="mb-3">
                <div class="row">
                    <div class="col-md-3">
                        <label class="form-label">Competencias aprendidas:</label>
                    </div>
                    <div class="col-md-9">
                        <div class="row">
                            <div class="col-md-6">
                                <div v-for="(competencia, index) in competenciasOptions.slice(0, Math.ceil(competenciasOptions.length / 2))" :key="index" class="d-flex align-items-center mb-2">
                                    <input type="checkbox" :id="'competencia-' + index" :value="competencia"
                                        v-model="localFormData.competencias" />
                                    <label :for="'competencia-' + index" class="ms-2">{{ competencia }}</label>
                                </div>
                            </div>
                            <div class="col-md-6">
                                <div v-for="(competencia, index) in competenciasOptions.slice(Math.ceil(competenciasOptions.length / 2))" :key="index" class="d-flex align-items-center mb-2">
                                    <input type="checkbox" :id="'competencia-' + (competenciasOptions.length / 2 + index)" :value="competencia"
                                        v-model="localFormData.competencias" />
                                    <label :for="'competencia-' + (competenciasOptions.length / 2 + index)" class="ms-2">{{ competencia }}</label>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="mb-3">
                <label for="opinion" class="form-label">Opinión</label>
                <textarea id="opinion" class="form-control" v-model="localFormData.opinion"></textarea>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: 'FormularioIngreso',
    props: {
        formData: Object,
    },
    data() {
        return {
            localFormData: { ...this.formData },
            competenciasOptions: [
                'Morfología de un componente',
                'One-Way y Two-Way data binding',
                'El patrón de diseño MVVM',
                'Directivas',
                'Estado'
            ]
        };
    },
    watch: {
        localFormData: {
            deep: true,
            handler(newVal) {
                this.$emit('update:formData', newVal);
            },
        },
    },
};
</script>

<style scoped>
.form-container {
    background-color: #000;
}
</style>
