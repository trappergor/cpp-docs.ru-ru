---
title: "Диспетчер визуализации | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Диспетчер визуализации"
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Диспетчер визуализации
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Диспетчер визуального представления объект, элементы управления внешний вид всего приложения.  Он работает как один класс, где можно поместить весь код рисования для приложения.  Библиотека MFC содержит несколько диспетчеров визуального представления.  Также можно создать собственный диспетчер визуального представления, если необходимо создать пользовательское представление для приложения.  Следующие изображений отображается такое же приложение при различных диспетчеров визуального представления включены.  
  
 ![MyApp, преобразованный CMFCVisualManagerWindows](../Image/VMWindows.png "VMWindows")  
MyApp, которое использует диспетчер визуального представления CMFCVisualManagerWindows  
  
 ![MyApp, преобразованный CMFCVisualManagerVS2005](../mfc/media/vmvs2005.png "VMVS2005")  
MyApp, которое использует диспетчер визуального представления CMFCVisualManagerVS2005  
  
 ![MyApp, преобразованный CMFCVisualManagerOfficeXP](../mfc/media/vmofficexp.png "VMOfficeXP")  
MyApp, которое использует диспетчер визуального представления CMFCVisualManagerOfficeXP  
  
 ![MyApp, преобразованный CMFCVisualManagerOffice2003](../mfc/media/vmoffice2003.png "VMOffice2003")  
MyApp, которое использует диспетчер визуального представления CMFCVisualManagerOffice2003  
  
 ![MyApp, преобразованный CMFCVisualManagerOffice2007](../mfc/media/msoffice2007.png "MSOffice2007")  
MyApp, которое использует диспетчер визуального представления CMFCVisualManagerOffice2007  
  
 По умолчанию диспетчер визуального представления поддерживает код окраски для нескольких элементов ГРАФИЧЕСКОГО ИНТЕРФЕЙСА ПОЛЬЗОВАТЕЛЯ.  Для предоставления пользовательских элементов пользовательского интерфейса необходимо переопределить соответствующие методы рисования диспетчера визуального представления.  Список этих методов см. в разделе [CMFCVisualManager Class](../mfc/reference/cmfcvisualmanager-class.md).  Методы, которые можно переопределить, чтобы реализовать пользовательский вид все методы, которые начинаются с `OnDraw`.  
  
 Приложение может иметь только один объект `CMFCVisualManager`.  Чтобы получить указатель на диспетчер визуального представления для приложения, вызовите статическая функция [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md).  Поскольку все диспетчеров визуального представления наследуются от `CMFCVisualManager`, метод `CMFCVisualManager::GetInstance` получает указатель к соответствующему диспетчеру визуального представления, даже если создается пользовательский диспетчер визуального представления.  
  
 Если необходимо создать пользовательский диспетчер визуального представления, необходимо наследовать его от диспетчера визуального представления, который уже существует.  Класс по умолчанию, который должен быть производным от `CMFCVisualManager`.  Однако можно использовать другой диспетчер визуального представления, если она лучше показано, что требуется для приложения.  Например, если требуется использовать диспетчер визуального представления `CMFCVisualManagerOffice2007`, но можно изменить только как разделители вид, можно создать пользовательский класс из `CMFCVisualManagerOffice2007`.  В этом сценарии необходимо переписать только методы для рисования разделителей.  
  
 2 Возможных способа использования конкретный диспетчер визуального представления для приложения.  Один из способов вызова метода [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md) и передать нужный диспетчер визуального представления в качестве параметра.  В следующем примере кода показано, как можно использовать диспетчер визуального представления `CMFCVisualManagerVS2005` с этим методом.  
  
```  
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));  
```  
  
 Другой способ — использовать диспетчер визуального представления в приложении для создания его вручную.  Затем приложение будет использовать этот новый диспетчер визуального представления по всей отрисовки.  Однако поскольку может существовать только один объект `CMFCVisualManager` для каждого приложения, удалять текущий диспетчер визуального представления перед созданием нового один.  В следующем примере, `CMyVisualManager` пользовательский диспетчер визуального представления, который является производным от `CMFCVisualManager`.  Следующий метод изменяет какой диспетчер визуального представления используется для отображения приложения, в зависимости от индекса:  
  
```  
void CMyApp::SetSkin (int index)  
{  
   if (CMFCVisualManager::GetInstance() != NULL)  
   {  
      delete CMFCVisualManager::GetInstance();  
   }  
  
   switch (index)  
   {  
   case DEFAULT_STYLE:  
      // The following statement creates a new CMFCVisualManager  
      CMFCVisualManager::GetInstance();  
      break;  
  
   case CUSTOM_STYLE:  
      new CMyVisualManager;  
      break;  
  
   default:  
      CMFCVisualManager::GetInstance();  
      break;  
   }  
  
   CMFCVisualManager::GetInstance()->RedrawAll();  
}  
```  
  
## См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)   
 [CMFCVisualManager Class](../mfc/reference/cmfcvisualmanager-class.md)