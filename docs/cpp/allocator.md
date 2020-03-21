---
title: allocator
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: 39708e8cfff7f61c3a3f763f87e1a3da36f0d4b1
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077255"
---
# <a name="allocator"></a>allocator

**Блок, относящийся только к системам Microsoft**

Спецификатор объявления **распределителя** можно применять к пользовательским функциям выделения памяти, чтобы сделать выделение видимым с помощью трассировки событий для Windows (ETW).

## <a name="syntax"></a>Синтаксис

```
   __declspec(allocator)
```

## <a name="remarks"></a>Примечания

Собственный профилировщик памяти в Visual Studio работает путем сбора данных событий ETW распределения, созданных во время выполнения. Распределители в CRT и пакете Windows SDK аннотированы на уровне исходного кода, что позволяет регистрировать их данные выделения. При написании собственных распределительов все функции, возвращающие указатель на только что выделенную память кучи, могут быть дополнены `__declspec(allocator)`, как показано в этом примере для myMalloc:

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

Дополнительные сведения см. [в разделе измерение использования памяти в Visual Studio](/visualstudio/profiling/memory-usage) и [пользовательские события кучи ETW для машинного кода](/visualstudio/profiling/custom-native-etw-heap-events).

**Завершение блока, относящегося только к системам Майкрософт**
