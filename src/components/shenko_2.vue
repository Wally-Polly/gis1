<template>
    <div class="slider-container">
      <!-- кнопка назад -->
      <div class="back-button" @click="navigateBack">
        <LeftOutlined class="icon-back" />
      </div>
  
      <div class="text-center text-white text-2xl font-bold mb-4">
        Уфимский университет науки и технологий
      </div>
  
      <!-- Картинка с предпросмотром -->
      <div class="relative  py-1 ">
        <a-image :preview="{ visible: false }" :width="400" src="./шк_уннит1.jpg" class="main-image"
          @click="visible = true" />
      </div>
  
      <div class="border-b-2 border-gray-300 w-full my-4"></div>
  
      <div class="h-50  rounded-xl px-4 py-4 text-white text-sm" style="background-color: rgb(64,84,148);">
        <p>
Посещение Музея авиационных двигателей, где собрана уникальная коллекция экспонатов, отражающая историю развития отрасли с 40-х годов прошлого века 
до наших дней. Здесь представлены практически все газотурбинные двигатели, выпускавшиеся в России и СССР. Познакомитесь 
с лабораторией «СКБ Формула студент», где учащиеся вуза работают над созданием прототипов спортивных автомобилей. Вы узнаете все о
двигателях внутреннего сгорания в гоночных машинах, познакомитесь с прототипами гоночных болидов, беспилотного транспорта, электро и 
гибридных силовых установок, разработок в области изделий из композитных материалов
        </P>
  
        <span>
            Адрес: ул. К.Маркса 12
        </span>
      </div>
  
      <!-- Скрытые изображения для предпросмотра -->
      <div style="display: none">
        <a-image-preview-group :preview="{ visible, onVisibleChange: (vis: boolean) => (visible = vis)  }">
          <a-image src="./шк_уннит1.jpg" />
          <a-image src="./шк_уннит2.jpg" />
          <a-image src="./шк_уннит3.jpg" />
        </a-image-preview-group>
      </div>
  
    </div>
  </template>
  

  <script lang="ts" setup>

  import { ref, defineEmits } from 'vue';
  import { LeftOutlined} from '@ant-design/icons-vue';
  
  const visible = ref(false);
  
  // Определяем событие для родительского компонента
  const emit = defineEmits(['navigateBack']);
  
  // Метод для возврата
  function navigateBack() {
    emit('navigateBack');
  }
  </script>
  
  <style scoped>
  /* Центрирование основного контейнера */
  .slider-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    /* background-color: #2c3e50; */
    padding: 20px;
    border-radius: 10px;
    width: 100%;
    max-width: 600px;
    margin: 0 auto;
    position: relative;
  }
  
  /* Настройки текста */
  .text-center {
    color: white;
    font-family: Arial, sans-serif;
  }
  
  /* Основное изображение */
  .main-image {
    border-radius: 10px;
    cursor: pointer;
  }
  
  .back-button {
    position: absolute;
    top: 10px;
    left: 10px;
    cursor: pointer;
    color: white;
    font-size: 24px;
  }
  
  /* Иконка для кнопки */
  .icon-back {
    font-size: 24px;
    color: white;
  }
  
  /* Добавьте тени и стиль для текста */
  .text-center {
    text-shadow: 0px 0px 6px rgba(0, 0, 0, 0.8);
    /* Тень для текста */
    margin-bottom: 20px;
  }
  </style>