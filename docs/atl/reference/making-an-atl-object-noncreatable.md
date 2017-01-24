---
title: "Применение к объекту ATL атрибута noncreatable | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.objects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "проекты ATL, несоздаваемые объекты"
  - "несоздаваемые объекты ATL"
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Применение к объекту ATL атрибута noncreatable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Можно изменить атрибуты COM\-объекта, основанного на библиотеке ATL, таким образом, что клиент не сможет создавать этот объект напрямую.  В таком случае объект будет возвращен посредством вызова метода в другом объекте, а не создан напрямую.  
  
### Применение к объекту ATL атрибута noncreatable  
  
1.  Удалите для выбранного объекта строку [OBJECT\_ENTRY\_AUTO](../Topic/OBJECT_ENTRY_AUTO.md).  Если требуется, чтобы объект нельзя было создавать непосредственно, но чтобы при этом регистрировался элемент управления, замените строку OBJECT\_ENTRY\_AUTO строкой [OBJECT\_ENTRY\_NON\_CREATEABLE\_EX\_AUTO](../Topic/OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO.md).  
  
2.  Добавьте атрибут [noncreatable](../../windows/noncreatable.md) в компонентный класс в IDL\-файле.  Например:  
  
    ```  
    [  
       uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),  
       helpstring("MyObject"),  
      noncreatable  
    ]  
    coclass MyObject  
    {  
       [default] interface IMyInterface;  
    }  
    ```  
  
## См. также  
 [мастер проектов ATL](../Topic/ATL%20Project%20Wizard.md)   
 [Типы проектов Visual C\+\+](../../ide/visual-cpp-project-types.md)   
 [Создание проектов для рабочего стола с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Конфигурации по умолчанию проекта ATL](../../atl/reference/default-atl-project-configurations.md)