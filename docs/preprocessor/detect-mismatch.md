---
title: detect_mismatch
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
ms.openlocfilehash: fb6f147f1591f010298e84cb28f05b40dafaeb63
ms.sourcegitcommit: 22f7c4a9b4fc2158fb5283810f15275803cafe10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2019
ms.locfileid: "54417633"
---
# <a name="detectmismatch"></a>detect_mismatch
Помещает запись в объект. Компоновщик проверяет эти записи на предмет наличия потенциальных несоответствий.

## <a name="syntax"></a>Синтаксис

```
#pragma detect_mismatch("name", "value")
```

## <a name="remarks"></a>Примечания

При компоновке проекта компоновщик создает ошибку `LNK2038`, если проект содержит 2 объекта с одинаковыми именами `name`, но разными значениями `value`. Используйте эту директиву #pragma для предотвращения компоновки несогласованных объектных файлов.

Имя и значение являются строковыми литералами и подчиняются правилам для строковых литералов в отношении escape-символов и объединения. Они чувствительны к регистру и не может содержать запятую, знак равенства, кавычки, или **null** символ.

## <a name="example"></a>Пример

В этом примере создаются два файла, имеющие разные номера версий для одной метки версии.

```cpp
// pragma_directive_detect_mismatch_a.cpp
#pragma detect_mismatch("myLib_version", "9")
int main ()
{
   return 0;
}

// pragma_directive_detect_mismatch_b.cpp
#pragma detect_mismatch("myLib_version", "1")
```

При компиляции обоих этих файлов с помощью командной строки `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` возникает ошибка `LNK2038`.

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
