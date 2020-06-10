---
title: Практическое руководство. Преобразование существующей ленты MFC в ресурс ленты
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
ms.openlocfilehash: 56f36c977453d338b9e9bbd2462c1a8830ffe258
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620057"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>Практическое руководство. Преобразование существующей ленты MFC в ресурс ленты

Ресурсы Ribbon легче визуализировать, изменять и обслуживать, чем ручно закодированные ленты. В этом разделе описывается преобразование ленты, закодированной вручную, в проекте MFC в ресурс ленты.

Необходимо иметь существующий проект MFC, имеющий код, использующий классы ленты MFC, например [класс CMFCRibbonBar](reference/cmfcribbonbar-class.md).

### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>Преобразование ленты MFC в ресурс ленты

1. В Visual Studio в существующем проекте MFC откройте исходный файл, в котором `CMFCRibbonBar` инициализируется объект. Как правило, это файл маинфрм. cpp. Добавьте следующий код после кода инициализации для ленты.

```
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");
```

   Сохраните и закройте файл.

1. Создайте и запустите приложение MFC, а затем в Блокноте откройте Риббонаутпут. txt и скопируйте его содержимое.

1. В Visual Studio в меню **проект** выберите команду **Добавить ресурс**. В диалоговом окне **Добавление ресурса** выберите **Лента** и нажмите кнопку **создать**.

   Visual Studio создает ресурс ленты и открывает его в режиме конструктора. Идентификатор ресурса ленты — IDR_RIBBON1, который отображается в **представление ресурсов**. Лента определена в XML-файле Ribbon1. mfcribbon-ms.

1. В Visual Studio откройте Ribbon1. mfcribbon-ms, удалите его содержимое, а затем вставьте содержимое файла Риббонаутпут. txt, скопированного ранее. Сохраните и закройте Ribbon1. mfcribbon-ms.

1. Снова откройте исходный файл, в котором инициализируется объект CMFCRibbonBar (обычно это маинфрм. cpp), и закомментируйте существующий код ленты. Добавьте следующий код после кода, который вы закомментируи.

```
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
```

1. Выполните сборку проекта и запустите программу.

## <a name="see-also"></a>См. также раздел

[Конструктор лент (MFC)](ribbon-designer-mfc.md)
