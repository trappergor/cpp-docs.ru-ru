---
title: Настройка оптимизации компилятора для проекта ATL
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.optimization
- vc.appwiz.ATL.vtable
helpviewer_keywords:
- ATL_DISABLE_NO_VTABLE macro
- ATL projects, compiler optimization
- ATL_NO_VTABLE macro
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
ms.openlocfilehash: 5b6620b73713886301e4efc29754cf407d9576f4
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812347"
---
# <a name="specifying-compiler-optimization-for-an-atl-project"></a>Настройка оптимизации компилятора для проекта ATL

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

Если _ATL_DISABLE_NO_VTABLE не определен, макрос ATL_NO_VTABLE развертывается `declspec(novtable)`. С помощью `declspec(novtable)`в классе объявление предотвращает vtable указателя, инициализируемый в классе конструктор и деструктор. При построении проекта компоновщик исключает таблицы vtable и все функции, к которым он указывает.

Необходимо использовать ATL_NO_VTABLE и, следовательно `declspec(novtable)`, только базовые классы, которые нельзя напрямую создать. Не следует использовать `declspec(novtable)` в классе самого дальнего в проекте, так как этот класс (обычно [CComObject](../../atl/reference/ccomobject-class.md), [CComAggObject](../../atl/reference/ccomaggobject-class.md), или [CComPolyObject](../../atl/reference/ccompolyobject-class.md)) Инициализирует указатель vtable для вашего проекта.

Не следует вызывать виртуальные функции из конструктора любого объекта, который использует `declspec(novtable)`. Эти вызовы следует переместить [FinalConstruct](ccomobjectrootex-class.md#finalconstruct) метод.

Если вы не уверены, следует ли использовать `declspec(novtable)` модификатор, можно удалить макрос ATL_NO_VTABLE из определений всех классов, или вы можете глобально отключить, указав

```
#define _ATL_DISABLE_NO_VTABLE
```

в файле stdafx.h прежде чем все другие ATL заголовочные файлы включены.

## <a name="see-also"></a>См. также

[Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Типы проектов Visual C++](../../build/reference/visual-cpp-project-types.md)<br/>
[Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[novtable](../../cpp/novtable.md)<br/>
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)
