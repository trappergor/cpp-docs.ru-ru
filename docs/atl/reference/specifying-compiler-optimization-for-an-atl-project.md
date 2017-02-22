---
title: "Задание оптимизации компилятора для проекта ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.optimization"
  - "vc.appwiz.ATL.vtable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "проекты ATL, оптимизация компилятора"
  - "ATL_DISABLE_NO_VTABLE - макрос"
  - "ATL_NO_VTABLE - макрос"
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Задание оптимизации компилятора для проекта ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

По умолчанию [Мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md) создает новые классы с помощью макроса ATL\_NO\_VTABLE следующим образом:  
  
```  
class ATL_NO_VTABLE CProjName  
{  
   ...  
};  
```  
  
 Затем библиотека ATL определяет макрос \_ATL\_NO\_VTABLE следующим образом:  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
   #define ATL_NO_VTABLE  
#else  
   #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 Если макрос \_ATL\_DISABLE\_NO\_VTABLE не определен, то макрос ATL\_NO\_VTABLE раскрывается в модификатора `declspec(novtable)`.  Использование модификатора `declspec(novtable)` в объявлении класса предотвращает инициализацию указателя vtable в конструкторе и деструкторе класса.  При построении проекта компоновщик исключает указатель vtable и все функции, на которые он указывает.  
  
 Необходимо использовать макрос ATL\_NO\_VTABLE и, следовательно, модификатор `declspec(novtable)` только с базовыми классами, которые нельзя создать напрямую.  Нельзя использовать модификатор `declspec(novtable)` с производным классом, дальше всего отстоящим от базового в проекте, поскольку этот класс \(обычно это [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md) или [CComPolyObject](../../atl/reference/ccompolyobject-class.md)\) инициализирует указатель vtable для проекта.  
  
 Нельзя вызывать виртуальные функции из конструктора любого объекта, использующего модификатор `declspec(novtable)`.  Необходимо перемещать эти вызовы в метод [FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md).  
  
 Если точно неизвестно, должен ли использоваться модификатор `declspec(novtable)`, то можно удалить макрос ATL\_NO\_VTABLE из определений всех классов, или отключить его глобально, указав:  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 В файле stdafx.h, перед включением всех других файлов заголовков ATL.  
  
## См. также  
 [мастер проектов ATL](../Topic/ATL%20Project%20Wizard.md)   
 [Типы проектов Visual C\+\+](../../ide/visual-cpp-project-types.md)   
 [Создание проектов для рабочего стола с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [Конфигурации по умолчанию проекта ATL](../../atl/reference/default-atl-project-configurations.md)