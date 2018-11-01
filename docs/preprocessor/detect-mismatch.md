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
ms.openlocfilehash: 2973a4738aa54e9f454190b18bcabff92077b284
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633328"
---
# <a name="detectmismatch"></a>detect_mismatch
Помещает запись в объект. Компоновщик проверяет эти записи на предмет наличия потенциальных несоответствий.

## <a name="syntax"></a>Синтаксис

```
#pragma detect_mismatch( "name", "value"))
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