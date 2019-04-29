---
title: Практическое руководство. Создание виртуальной схемы сообщений для класса шаблона
ms.date: 11/04/2016
helpviewer_keywords:
- template classes [MFC], creating message maps
- message maps [MFC], template classes
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
ms.openlocfilehash: 676e698a899327eee8305731b5d609b5b95ece76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389506"
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>Практическое руководство. Создание виртуальной схемы сообщений для класса шаблона

Сопоставление сообщений в MFC предоставляет эффективный способ для направления сообщений Windows соответствующий экземпляр объекта C++. Целевые объекты карты сообщения MFC примеры классы приложения, документа и Просмотр классов, классы элементов управления и т. д.

Традиционные схемы сообщений MFC объявляются с помощью [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) макрос для объявления начала схему сообщений, запись макроса для каждого метода класс обработчика сообщений и, наконец [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)макрос для объявления в конец схемы сообщений.

Одно ограничение с [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) макрос происходит, когда он используется в сочетании с класс, содержащий аргументы шаблона. При использовании с классом шаблона, этот макрос приведет к ошибке времени компиляции из-за отсутствующих параметров шаблона во время расширения макроса. [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map) макрос разработана для обеспечения сопоставляет классы, содержащие аргументом один шаблон для объявления свои собственные сообщения.

## <a name="example"></a>Пример

Рассмотрим пример, где MFC [CListBox](../mfc/reference/clistbox-class.md) класс расширяется для синхронизации с внешним источником данных. Вымышленный `CSyncListBox` класс объявляется следующим образом:

[!code-cpp[NVC_MFC_CListBox#42](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]

`CSyncListBox` Класс является шаблоном для одного типа, описывающий оно синхронизируется с источником данных. Он также объявляет три метода, которые будут участвовать в схеме сообщений класса: `OnPaint`, `OnDestroy`, и `OnSynchronize`. `OnSynchronize` Метод реализуется следующим образом:

[!code-cpp[NVC_MFC_CListBox#43](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]

Выше реализация позволяет `CSyncListBox` класс специализированным на любой тип класса, реализующий `GetCount` метод, такой как `CArray`, `CList`, и `CMap`. `StringizeElement` Функция является функцией-шаблоном прототипом, следующие:

[!code-cpp[NVC_MFC_CListBox#44](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]

Как правило сопоставление сообщений для этого класса будет определено так:

```cpp
BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)
  ON_WM_PAINT()
  ON_WM_DESTROY()
  ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)
END_MESSAGE_MAP()
```

где **LBN_SYNCHRONIZE** настраиваемого пользовательского сообщения определяется приложением, такие как:

[!code-cpp[NVC_MFC_CListBox#45](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]

Выше макроса карты не будет компилироваться, связано с тем фактом, что спецификация шаблона для `CSyncListBox` класса будут отсутствовать во время расширения макроса. **BEGIN_TEMPLATE_MESSAGE_MAP** макрос устраняет эту проблему путем включения параметра указанного шаблона в сопоставление расширенным макросом. Сопоставление сообщений для этого класса принимает следующий вид:

[!code-cpp[NVC_MFC_CListBox#46](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]

Следующий подход демонстрирует пример использования `CSyncListBox` используя `CStringList` объекта:

[!code-cpp[NVC_MFC_CListBox#47](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]

Чтобы завершить проверку, `StringizeElement` функцию, специализированную для работы с `CStringList` класса:

[!code-cpp[NVC_MFC_CListBox#48](../mfc/codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]

## <a name="see-also"></a>См. также

[BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)<br/>
[Обработка и сопоставление сообщений](../mfc/message-handling-and-mapping.md)
