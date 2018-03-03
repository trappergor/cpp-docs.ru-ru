---
title: "Как: преобразование существующей ленты MFC в ресурс ленты | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7cb0d5d80edd52a85834963d030e35eef96d718
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>Практическое руководство. Преобразование существующей ленты MFC в ресурс ленты
Ресурсы ленты, проще визуализировать, изменение и обслуживание от вручную закодированная лент. В этом разделе описывается преобразование вручную закодированная лента в проекте MFC в ресурс ленты.  
  
 Необходимо иметь проект MFC, имеет код, который использует классы ленты MFC, например, [CMFCRibbonBar класса](../mfc/reference/cmfcribbonbar-class.md).  
  
### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>Чтобы преобразовать ленты MFC в ресурс ленты  
  
1.  В Visual Studio в существующий проект MFC, откройте исходный файл, где CMFCRibbonBar объект инициализирован. Как правило файл является mainfrm.cpp. Добавьте следующий код после кода инициализации для ленты.  
  
 ```  
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");

 ```  
  
     Сохраните и закройте файл.  
  
2.  Построение и запуск приложения MFC в блокноте откройте RibbonOutput.txt и скопируйте его содержимое.  
  
3.  В Visual Studio на **проекта** меню, нажмите кнопку **добавить ресурс**. В **добавить ресурс** выберите **ленты** и нажмите кнопку **New**.  
  
     Visual Studio создает ресурс ленты и открывает его в режиме конструктора. Идентификатор ресурса ленты — IDR_RIBBON1, который отображается в **представление ресурсов**. Ленты, определен в XML-файле ribbon1.mfcribbon ms.  
  
4.  В Visual Studio откройте ribbon1.mfcribbon ms, удалите его содержимое, а затем вставьте содержимое RibbonOutput.txt, который был скопирован ранее. Сохраните и закройте ribbon1.mfcribbon мс.  
  
5.  Снова откройте исходный файл, где инициализации объекта CMFCRibbonBar (как правило, mainfrm.cpp) и закомментируйте существующего кода ленты. Добавьте следующий код после кода, вы в комментарий.  
  
 ```  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);

 ```  
  
6.  Выполните построение проекта и запустите программу.  
  
## <a name="see-also"></a>См. также  
 [Конструктор ленты (MFC)](../mfc/ribbon-designer-mfc.md)

