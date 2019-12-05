---
title: allocator
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: 2e2615829f6491bf660859fbc86ebcd07a56c5fe
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857688"
---
# <a name="allocator"></a>allocator

**Блок, относящийся только к системам Майкрософт**

Спецификатор объявления **распределителя** можно применять к пользовательским функциям выделения памяти, чтобы сделать выделение видимым с помощью трассировки событий для Windows (ETW).

## <a name="syntax"></a>Синтаксис

```
   __declspec(allocator) 
```

## <a name="remarks"></a>Заметки

Собственный профилировщик памяти в Visual Studio работает путем сбора данных событий ETW распределения, созданных во время выполнения. Распределители в CRT и пакете Windows SDK аннотированы на уровне исходного кода, что позволяет регистрировать их данные выделения. При написании собственных распределительов все функции, возвращающие указатель на только что выделенную память кучи, могут быть дополнены `__declspec(allocator)`, как показано в этом примере для myMalloc:

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

Дополнительные сведения см. [в разделе измерение использования памяти в Visual Studio](/visualstudio/profiling/memory-usage) и [пользовательские события кучи ETW для машинного кода](/visualstudio/profiling/custom-native-etw-heap-events).

**Завершение блока, относящегося только к системам Майкрософт**
