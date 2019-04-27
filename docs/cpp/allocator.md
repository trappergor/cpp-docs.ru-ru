---
title: allocator
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: f9c8de7c8686b89a2ab9570a2558e3f649e545b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155242"
---
# <a name="allocator"></a>allocator

**Блок, относящийся только к системам Microsoft**

**Распределителя** спецификатора объявления могут применяться к функциям пользовательского выделения памяти для отображения распределения с помощью событий трассировки для Windows (ETW).

## <a name="syntax"></a>Синтаксис

```
   __declspec(allocator) 
```

## <a name="remarks"></a>Примечания

В Visual Studio профилировщик внутренней памяти работает путем сбора выделения данные событий трассировки событий Windows, создаваемых во время выполнения. Распределители в CRT и пакете Windows SDK аннотированы на уровне исходного кода, что позволяет регистрировать их данные выделения. Если вы создаете собственные Распределители, то любые функции, возвращающие указатель на только что выделенную память в куче может быть снабжен атрибутом `__declspec(allocator)`, как показано в этом примере для myMalloc:

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

Дополнительные сведения см. в разделе [Оцените потребление памяти в Visual Studio](/visualstudio/profiling/memory-usage) и [Custom собственные события трассировки событий Windows кучи](/visualstudio/profiling/custom-native-etw-heap-events).