---
title: Прагма strict_gs_check
ms.date: 08/29/2019
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
ms.openlocfilehash: 0b66e87f2280c923d05103fccfcbbc8d32daf3fd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216581"
---
# <a name="strict_gs_check-pragma"></a>Прагма strict_gs_check

Эта директива #pragma обеспечивает усиленную проверку безопасности.

## <a name="syntax"></a>Синтаксис

> **#pragma strict_gs_check (** [ **Push,** ] { **On** | **Off** } **)** \
> **#pragma strict_gs_check (POP)**

## <a name="remarks"></a>Примечания

Заставляет компилятор вставлять случайные объекты cookie в стек функции, помогая обнаруживать некоторые категории переполнения буфера на основе стека. По умолчанию `/GS` параметр компилятора (проверка безопасности буфера) не вставляет файл cookie для всех функций. Дополнительные сведения см. в разделе [Параметр /GS (проверка безопасности буфера)](../build/reference/gs-buffer-security-check.md).

Скомпилируйте с помощью `/GS` , чтобы включить **strict_gs_check**.

Используйте эту директиву #pragma в модулях кода, которые могут получать потенциально вредоносные данные. **strict_gs_check** является агрессивной директивой pragma и применяется к функциям, которые могут не нуждаться в этой защите, но оптимизированы для снижения воздействия на производительность результирующего приложения.

Даже при использовании этой директивы #pragma следует стремиться к созданию защищенного программного кода. То есть убедитесь, что в коде нет переполнения буфера. **strict_gs_check** может защитить приложение от переполнения буфера, которые остаются в коде.

## <a name="example"></a>Пример

В этом примере переполнение буфера возникает при копировании массива в локальный массив. При компиляции этого кода `/GS`в стек не вставляется файл cookie, поскольку тип данных массива является указателем. Добавление директивы pragma **strict_gs_check** приводит к принудительному вызову файла cookie стека в стеке функций.

```cpp
// pragma_strict_gs_check.cpp
// compile with: /c

#pragma strict_gs_check(on)

void ** ReverseArray(void **pData,
                     size_t cData)
{
    // *** This buffer is subject to being overrun!! ***
    void *pReversed[20];

    // Reverse the array into a temporary buffer
    for (size_t j = 0, i = cData; i ; --i, ++j)
        // *** Possible buffer overrun!! ***
            pReversed[j] = pData[i];

    // Copy temporary buffer back into input/output buffer
    for (size_t i = 0; i < cData ; ++i)
        pData[i] = pReversed[i];

    return pData;
}
```

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[/GS (проверка безопасности буфера)](../build/reference/gs-buffer-security-check.md)
