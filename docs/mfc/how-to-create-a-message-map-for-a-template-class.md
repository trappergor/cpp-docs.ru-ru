---
title: Практическое руководство. Создание виртуальной схемы сообщений для класса шаблона
ms.date: 11/04/2016
helpviewer_keywords:
- template classes [MFC], creating message maps
- message maps [MFC], template classes
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
ms.openlocfilehash: 65ddc77b4e8fd466c7d651e54e93a504b4858da1
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620049"
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>Практическое руководство. Создание виртуальной схемы сообщений для класса шаблона

Сопоставление сообщений в MFC обеспечивает эффективный способ направления сообщений Windows в соответствующий экземпляр объекта C++. Примеры целевых объектов схемы сообщений MFC включают классы приложений, классы документов и представлений, классы элементов управления и т. д.

Традиционные схемы сообщений MFC объявляются с помощью макроса [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) , чтобы объявить начало схемы сообщения, запись макроса для каждого метода класса обработчика сообщений и, наконец, макрос [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) для объявления конца схемы сообщения.

При использовании макроса [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) возникает одно ограничение, если оно используется в сочетании с классом, содержащим аргументы шаблона. При использовании с классом шаблона этот макрос вызывает ошибку во время компиляции из-за отсутствующих параметров шаблона во время расширения макроса. Макрос [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map) был разработан таким образом, чтобы позволить классам, содержащим один аргумент шаблона, объявлять свои собственные карты сообщений.

## <a name="example"></a>Пример

Рассмотрим пример, в котором класс [CLISTBOX](reference/clistbox-class.md) MFC расширен для обеспечения синхронизации с внешним источником данных. Вымышленный `CSyncListBox` класс объявляется следующим образом:

[!code-cpp[NVC_MFC_CListBox#42](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]

`CSyncListBox`Класс является шаблоном для одного типа, который описывает источник данных, с которым будет выполняться синхронизация. Он также объявляет три метода, которые будут участвовать в схеме сообщений класса: `OnPaint` , `OnDestroy` и `OnSynchronize` . `OnSynchronize`Метод реализуется следующим образом:

[!code-cpp[NVC_MFC_CListBox#43](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]

Приведенная выше реализация позволяет `CSyncListBox` классу быть специализированным для любого типа класса, реализующего `GetCount` метод, например `CArray` , `CList` и `CMap` . `StringizeElement`Функция является шаблонной функцией, прототипом которой является следующим:

[!code-cpp[NVC_MFC_CListBox#44](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]

Как правило, схема сообщений для этого класса будет определяться следующим образом:

```cpp
BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)
  ON_WM_PAINT()
  ON_WM_DESTROY()
  ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)
END_MESSAGE_MAP()
```

где **LBN_SYNCHRONIZE** — это пользовательское сообщение, определяемое приложением, например:

[!code-cpp[NVC_MFC_CListBox#45](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]

Приведенная выше схема макроса не будет компилироваться из-за того, что спецификация шаблона для `CSyncListBox` класса будет отсутствовать во время расширения макроса. Макрос **BEGIN_TEMPLATE_MESSAGE_MAP** решает эту проблему, добавляя указанный параметр шаблона в развернутую карту макросов. Схема сообщений для этого класса выглядит следующим образом:

[!code-cpp[NVC_MFC_CListBox#46](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]

Ниже демонстрируется пример использования `CSyncListBox` класса с помощью `CStringList` объекта:

[!code-cpp[NVC_MFC_CListBox#47](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]

Для выполнения теста `StringizeElement` функция должна быть специализированной для работы с `CStringList` классом:

[!code-cpp[NVC_MFC_CListBox#48](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]

## <a name="see-also"></a>См. также раздел

[BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)<br/>
[Обработка и сопоставление сообщений](message-handling-and-mapping.md)
