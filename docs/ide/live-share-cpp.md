---
title: Совместная работа с использованием Live Share для C++
description: Узнайте, как использовать Live Share для C++ в Visual Studio для совместной работы и совместного использования кода в реальном времени.
ms.date: 05/24/2019
ms.openlocfilehash: e8202cefb7f7d762e2736edcd5fa3c6127b4affa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171922"
---
# <a name="collaborate-using-live-share-for-c"></a>Совместная работа с использованием Live Share для C++

В Visual Studio 2019 и Visual Studio Code можно использовать **Live Share** для совместной работы над проектами C++ в реальном времени. С помощью **Live Share** ваш код могут редактировать и отлаживать другие пользователи без необходимости устанавливать проект или его зависимости. Вы можете просматривать изменения по мере их внесения. Каждое изменение обозначается именем его создателя.

![Редактирование&#43; &#43; Live Share в C](../ide/media/live-share-edit-cpp.png "Live Share редактирования вC++")

## <a name="live-share-host-and-guests"></a>Организатор и гости Live Share

В каждом сеансе Live Share есть организатор и один или несколько гостей. И организатор, и гости системами могут использовать Visual Studio или Visual Studio Code. Организатор, использующий Visual Studio 2019 в Windows, может совместно работать с гостем, использующим Visual Studio Code в Linux.

Организатор предоставляет гостям все необходимое для продуктивной работы. Гостям не нужно иметь исходный кода, компилятор, внешние зависимости и соответствующие установленные компоненты.

И организатор, и гости могут использовать следующие функции IntelliSense:

- список членов;
- Справка по параметрам
- краткие сведения
- отладка и использование точек останова;
- Найти все ссылки
- Перейти к определению
- поиск символов (CTRL+T);
- Выделение ссылок
- диагностика, поиск ошибок и использование волнистых линий.

![Отладка C&#43; &#43; Live Share](../ide/media/live-share-debug-cpp.png "Отладка Live Share вC++")

## <a name="start-and-end-a-live-share-session"></a>Запуск и завершение сеанса Live Share

Чтобы запустить сеанс Live Share в Visual Studio, нажмите кнопку "Совместно использовать" в правом верхнем углу или выберите **Файл** > **Начать сеанс совместной работы**. Будет создана ссылка, которой вы можете поделиться с другими пользователями.

![Кнопка&#43; &#43; Live Share C](../ide/media/live-share-button-cpp.png "Кнопка Live Share")

Чтобы завершить сеанс, выберите **Завершить сеанс совместной работы** в раскрывающемся списке **Общий доступ**.

![Кнопка&#43; &#43; Live Share C](../ide/media/live-share-end-session-cpp.png "Кнопка Live Share")

## <a name="for-more-information"></a>Дополнительные сведения

См. подробнее о **Live Share** в Visual Studio в описании [новых возможностей Visual Studio Live Share](/visualstudio/liveshare/). См. подробнее об использовании [Live Share](https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare) в Visual Studio Code.

## <a name="see-also"></a>См. также:

[Редактирование и рефакторинг кода C++](writing-and-refactoring-code-cpp.md)</br>
[Перемещение по базе кода С++ в Visual Studio](navigate-code-cpp.md)</br>
[Чтение и понимание кода C++](read-and-understand-code-cpp.md)</br>
