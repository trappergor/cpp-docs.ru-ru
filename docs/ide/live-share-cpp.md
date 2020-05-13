---
title: Совместная работа с использованием Live Share для C++
description: Узнайте, как использовать Live Share для C++ в Visual Studio для совместной работы и совместного использования кода в реальном времени.
ms.date: 05/24/2019
ms.openlocfilehash: 0ebdd77d0e277778b48cf69024b24841f775d968
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377288"
---
# <a name="collaborate-using-live-share-for-c"></a>Совместная работа с использованием Live Share для C++

В Visual Studio 2019 и Visual Studio Code можно использовать **Live Share** для совместной работы над проектами C++ в реальном времени. С помощью **Live Share** ваш код могут редактировать и отлаживать другие пользователи без необходимости устанавливать проект или его зависимости. Вы можете просматривать изменения по мере их внесения. Каждое изменение обозначается именем его создателя.

![C&#43;&#43; Live Доля Редактирование](../ide/media/live-share-edit-cpp.png "Редактирование акций в реальном времени в СЗ")

## <a name="live-share-host-and-guests"></a>Организатор и гости Live Share

В каждом сеансе Live Share есть организатор и один или несколько гостей. И организатор, и гости системами могут использовать Visual Studio или Visual Studio Code. Организатор, использующий Visual Studio 2019 в Windows, может совместно работать с гостем, использующим Visual Studio Code в Linux.

Организатор предоставляет гостям все необходимое для продуктивной работы. Гостям не нужно иметь исходный кода, компилятор, внешние зависимости и соответствующие установленные компоненты.

И организатор, и гости могут использовать следующие функции IntelliSense:

- список членов;
- Справка по параметрам
- Краткие сведения
- отладка и использование точек останова;
- Найти все ссылки
- Перейти к определению
- поиск символов (CTRL+T);
- Выделение ссылок
- диагностика, поиск ошибок и использование волнистых линий.

![C&#43;&#43; Live Доля Debugging](../ide/media/live-share-debug-cpp.png "Отладка live Share в СЗ")

## <a name="start-and-end-a-live-share-session"></a>Запуск и завершение сеанса Live Share

Чтобы начать сеанс Live Share в Visual Studio, нажмите кнопку «Поделиться» в правом верхнем ряде или перейдите на**сеанс начала работы** **с файлами.** >  Будет создана ссылка, которой вы можете поделиться с другими пользователями.

![C&#43;&#43; Live Кнопка обмена](../ide/media/live-share-button-cpp.png "Кнопка live Share")

Чтобы завершить сеанс, выберите **Завершить сеанс совместной работы** в раскрывающемся списке **Общий доступ**.

![C&#43;&#43; Live Кнопка обмена](../ide/media/live-share-end-session-cpp.png "Кнопка live Share")

## <a name="for-more-information"></a>Дополнительные сведения

См. подробнее о **Live Share** в Visual Studio в описании [новых возможностей Visual Studio Live Share](/visualstudio/liveshare/). См. подробнее об использовании [Live Share](https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare) в Visual Studio Code.

## <a name="see-also"></a>См. также:

[Редактирование и рефакторинг кода C++](writing-and-refactoring-code-cpp.md)</br>
[Перемещение по базе кода С++ в Visual Studio](navigate-code-cpp.md)</br>
[Чтение и понимание кода C++](read-and-understand-code-cpp.md)</br>
