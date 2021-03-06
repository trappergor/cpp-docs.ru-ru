---
title: Добавление универсального класса C++
ms.date: 11/09/2018
f1_keywords:
- vc.codewiz.classes.adding.generic
- vc.codewiz.class.generic
helpviewer_keywords:
- Visual C++, classes
- generic classes, adding
- generic classes
- generic C++ class wizard [C++]
ms.assetid: e95a5a14-dbed-4edc-8551-344fe48613cb
ms.openlocfilehash: d5c00a35e375d133fbd3a6ed7fe3591e4b0cd54b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503125"
---
# <a name="add-a-generic-c-class"></a>Добавление универсального класса C++

Универсальный класс C++ можно добавить с помощью **представления классов**. Универсальный класс C++ — это класс, который определен вами, или производный от него.

**Добавление универсального класса C++ в проект**

1. В **представлении классов** щелкните правой кнопкой мыши проект, куда вы хотите добавить новый класс, а затем выберите **Добавить** и **Класс**.

1. В области шаблонов диалогового окна [Добавление класса](./adding-a-class-visual-cpp.md#add-class-dialog-box) выберите **Класс C++** . Нажмите кнопку **Добавить**, чтобы отобразить [Общий мастер класса C++](#generic-c-class-wizard).

1. В мастере укажите имя класса и определите параметры или примите значения по умолчанию.

1. Чтобы закрыть мастер и просмотреть новый универсальный класс C++ в проекте, нажмите кнопку **Готово**.

## <a name="in-this-section"></a>В этом разделе

- [Мастер универсальных классов C++](#generic-c-class-wizard)

## <a name="generic-c-class-wizard"></a>Мастер универсальных классов C++

Добавляет универсальный класс C++ в проект. Этот класс не наследует от ATL или MFC.

- **Имя класса**

  Задает имя нового файла.

- **H-файл**

  Задает имя файла заголовка для нового класса. По умолчанию это имя основано на имени, указанном в поле **Имя класса**. Чтобы сохранить файл заголовка в выбранном расположении или добавить объявление класса к существующему файлу, нажмите кнопку с многоточием ( **...** ). Если указать существующий файл и нажать кнопку **Готово** мастер предложит указать, нужно ли добавить объявление класса к содержимому файла. Чтобы добавить объявление, нажмите кнопку **Да**; чтобы вернуться в мастер и указать другое имя файла, нажмите кнопку **Нет**.

- **CPP-файл**

  Задает имя файла реализации для нового класса. По умолчанию это имя основано на имени, указанном в поле **Имя класса**. Чтобы сохранить файл реализации в выбранном расположении или добавить определение класса к существующему файлу, нажмите кнопку с многоточием ( **...** ). Если указать существующий файл и нажать кнопку **Готово** мастер предложит указать, нужно ли добавить определение класса к содержимому файла. Чтобы добавить определение, нажмите кнопку **Да**; чтобы вернуться в мастер и указать другое имя файла, нажмите кнопку **Нет**.

- **Базовый класс**

  Задает базовый класс для нового класса.

- **Доступ**

  Задает доступ к членам базового класса для нового класса. Модификаторы доступа — это ключевые слова, которые определяют уровень доступа других классов к функциям-членам класса. Дополнительные сведения об указании доступа см. в разделе [Управление доступом к членам](../cpp/member-access-control-cpp.md). По умолчанию уровень доступа класса имеет значение **`public`** .

  - **`public`**
  - **`protected`**
  - **`private`**
  - **По умолчанию** (модификатор доступа не создается).

- **Виртуальный деструктор**

  Указывает, является ли деструктор класса виртуальным. Использование виртуального деструктора помогает обеспечить вызов подходящего деструктора при удалении экземпляров производных классов.

- **Встроенный**

  Создает конструктор классов и определение класса в виде встраиваемых функций в файле заголовка.

- **Управляемый**

  Когда установлен, добавляет управляемый класс и файл заголовка. Когда снят, добавляет собственный класс и файл заголовка.
