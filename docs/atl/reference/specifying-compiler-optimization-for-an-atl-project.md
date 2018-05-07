---
title: Задание оптимизации компилятора для проекта ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0060437613bcdd6281ce5cceb112f5fd7f470bf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
  
 Если _ATL_DISABLE_NO_VTABLE не определен, макрос ATL_NO_VTABLE развертывается `declspec(novtable)`. С помощью `declspec(novtable)`в классе объявление предотвращает vtable указателя, инициализируемый в конструкторе и деструкторе класса. При построении проекта компоновщик исключает указатель vtable и все функции, на которые он указывает.  
  
 Необходимо использовать макрос ATL_NO_VTABLE и, следовательно, `declspec(novtable)`, только базовые классы, которые нельзя непосредственно создать. Не следует использовать `declspec(novtable)` с более низкого уровня класса в проекте, так как этот класс (обычно [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), или [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) Инициализирует указатель vtable для проекта.  
  
 Нельзя вызывать виртуальные функции из конструктора любого объекта, который использует `declspec(novtable)`. Следует переместить эти вызовы [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) метод.  

  
 Если вы не уверены, следует ли использовать `declspec(novtable)` модификатор, можно удалить макрос ATL_NO_VTABLE из определений всех классов, или можно глобально отключить его, указав  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
 в файле stdafx.h перед другими ATL заголовочные файлы включены.  
  
## <a name="see-also"></a>См. также  
 [Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)   
 [Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)   
 [Создание проектов для рабочего стола с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Основные принципы работы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)

