---
title: Практическое руководство. Преобразование существующей ленты MFC в ресурс ленты
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
ms.openlocfilehash: 627c50758b10ad18e45fc1432340c0eb2dad7b19
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524369"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>Практическое руководство. Преобразование существующей ленты MFC в ресурс ленты

Ресурсы ленты, проще визуализировать, изменения и эксплуатации, чем вручную закодированная лент. В этом разделе описывается преобразование вручную закодированная лента в проекте MFC в ресурс ленты.

Необходимо иметь существующий проект MFC, который содержит код, который использует классы ленты MFC, например [класс CMFCRibbonBar](../mfc/reference/cmfcribbonbar-class.md).

### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>Для преобразования ленты MFC в ресурс ленты

1. В Visual Studio, откройте исходный файл в существующем проекте MFC, где `CMFCRibbonBar` инициализации объекта. Как правило файл является mainfrm.cpp. Добавьте следующий код после кода инициализации для ленты.

```
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");
```

   Сохраните и закройте файл.

1. Построение и запуск приложения MFC, в блокноте откройте RibbonOutput.txt и скопируйте его содержимое.

1. В Visual Studio на **проекта** меню, щелкните **добавить ресурс**. В **добавить ресурс** выберите **ленты** и нажмите кнопку **New**.

   Visual Studio создает ресурс ленты и открывает его в режиме конструктора. Идентификатор ресурса ленты — IDR_RIBBON1, который отображается в **представление ресурсов**. Ленты, определяется в XML-файле ribbon1.mfcribbon-ms.

1. В Visual Studio откройте ribbon1.mfcribbon-ms, удалите его содержимое и вставьте содержимое RibbonOutput.txt, который вы скопировали ранее. Сохраните и закройте ribbon1.mfcribbon-ms.

1. Снова откройте исходный файл, где инициализируется объект CMFCRibbonBar (как правило, mainfrm.cpp) и закомментируйте существующий код ленте. Добавьте следующий код после кода, вы в комментарий.

```
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
```

1. Постройте проект и запустите программу.

## <a name="see-also"></a>См. также

[Конструктор ленты (MFC)](../mfc/ribbon-designer-mfc.md)

