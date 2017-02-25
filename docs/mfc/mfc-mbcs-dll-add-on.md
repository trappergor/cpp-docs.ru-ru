---
title: "Надстройка DLL MBCS MFC | Microsoft Docs"
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
  - "MBCS"
  - "MFC"
ms.assetid: bebec0ff-e019-42ca-b5df-8c218ac5b54a
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Надстройка DLL MBCS MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В Visual Studio 2015 библиотека MFC для многобайтовой кодировки \(MBCS\) входит в набор компонентов установки Visual C\+\+. Visual C\+\+ и MFC относятся к необязательным компонентам в программе установки Visual Studio. Чтобы убедиться в том, что компонент MFC установлен, в программе установки установите переключатель **Выборочная** и в разделе **Языки программирования** убедитесь, что выбраны пункты **Visual C\+\+** и **Microsoft Foundation Classes для C\+\+**. Если вы уже установили Visual Studio, при попытке создания проекта MFC вам будет предложено установить Visual C\+\+ и \(или\) MFC.  
  
 Для построения проекта MFC в Visual Studio 2015, в котором для свойства **Кодировка** установлено значение **Использовать многобайтовую кодировку** или **Не задано**, требуются многобайтовые библиотеки DLL.  
  
## См. также  
 [Версии библиотек MFC](../mfc/mfc-library-versions.md)