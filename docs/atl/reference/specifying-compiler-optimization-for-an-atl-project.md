---
title: "Задание оптимизации компилятора для проекта ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
dev_langs:
- C++
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: abdad4367e75c1971ba5d11af1a60992d1bb3dd4
ms.lasthandoff: 02/24/2017

---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>Задание оптимизации компилятора для проекта ATL
По умолчанию [мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md) создает новые классы с помощью макроса ATL_NO_VTABLE следующим образом:  
  
```  
class ATL_NO_VTABLE CProjName  
{  
 ...  
};  
```  
  
 Затем библиотека ATL определяет макрос _ATL_NO_VTABLE следующим образом:  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
 #define ATL_NO_VTABLE  
#else  
 #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 Если _ATL_DISABLE_NO_VTABLE не определен, макрос ATL_NO_VTABLE развертывается `declspec(novtable)`. С помощью `declspec(novtable)`в классе объявление предотвращает указателя vtable инициализацию в конструкторе и деструкторе класса. При построении проекта компоновщик исключает указатель vtable и все функции, на которые он указывает.  
  
 Необходимо использовать макрос ATL_NO_VTABLE и, следовательно, `declspec(novtable)`, с помощью только базовые классы, которые нельзя создать напрямую. Не следует использовать `declspec(novtable)` в классе самого дальнего в проекте, так как этот класс (обычно [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), или [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) инициализирует указателя vtable для проекта.  
  
 Нельзя вызывать виртуальные функции из конструктора любого объекта, использующего `declspec(novtable)`. Следует переместить эти вызовы [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) метод.  

  
 Если вы не уверены, следует ли использовать `declspec(novtable)` модификатор, то можно удалить макрос ATL_NO_VTABLE из определений всех классов, или вы можете глобально отключить, указав  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 Добавьте в файл stdafx.h перед другими ATL заголовочные файлы включены.  
  
## <a name="see-also"></a>См. также  
 [Мастер проекта ATL](../../atl/reference/atl-project-wizard.md)   
 [Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)   
 [Создание проектов для настольных ПК с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Программирование с использованием ATL и кода времени выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Основы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [Конфигурации проекта ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)


