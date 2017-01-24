---
title: "Функция-член InitInstance | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "InitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "приложения [MFC], инициализация"
  - "инициализация приложений MFC"
  - "InitInstance - метод"
  - "MFC [C++], инициализация"
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция-член InitInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Операционная система Windows позволяет выполнять более одной копии или экземпляр «,» одного приложения.  `WinMain` вызывает [InitInstance](../Topic/CWinApp::InitInstance.md) каждый раз новым экземпляром запуска приложения.  
  
 Реализация `InitInstance` стандарта, созданную с помощью мастера приложений MFC выполняет следующие задачи:  
  
-   Как и действие, является создание шаблонов документов, в свою очередь, создают документы, представления и фреймовые окна.  Описание этого процесса см. в разделе [Создание шаблона документа](../Topic/Document%20Template%20Creation.md).  
  
-   Параметры загрузки из INI\-файла стандартного файла или реестра Windows, включая имена последних использовавшийся ся файлов.  
  
-   Регистрирует один или несколько шаблонов документов.  
  
-   Для приложения MDI создает главного фреймовое окно.  
  
-   Процессы командной строки, чтобы открыть документ, указанный в командной строке или открыть новый пустой документ.  
  
 Можно добавить собственный код инициализации или изменить код, написанный мастером.  
  
> [!NOTE]
>  Приложения MFC должен быть инициализирован в однопотоковое подразделение \(STA\).  Если вызывается метод [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) в переопределении `InitInstance`, укажите `COINIT_APARTMENTTHREADED` \(а не `COINIT_MULTITHREADED`\).  Дополнительные сведения см. в PRB: Приложение MFC перестает отвечать при инициализации приложения как многопоточный апартамент \(828643\) в [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;828643](http://support.microsoft.com/default.aspx?scid=kb;en-us;828643).  
  
## См. также  
 [CWinApp: класс приложений](../Topic/CWinApp:%20The%20Application%20Class.md)