---
title: Прагма detect_mismatch
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
ms.openlocfilehash: 6e247b3f251bce47710a3380fb295597314a3bd8
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222391"
---
# <a name="detect_mismatch-pragma"></a>Прагма detect_mismatch

Помещает запись в объект. Компоновщик проверяет эти записи на предмет наличия потенциальных несоответствий.

## <a name="syntax"></a>Синтаксис

> **#pragma detect_mismatch (** "*Name*" **,** "*value*" **)**

## <a name="remarks"></a>Примечания

При связывании проекта компоновщик создает ошибку [LNK2038](../error-messages/tool-errors/linker-tools-error-lnk2038.md) , если проект содержит два объекта с одинаковым *именем* , но у каждого из них другое *значение*. Используйте эту директиву #pragma для предотвращения компоновки несогласованных объектных файлов.

И *имя* , и *значение* являются строковыми литералами и подчиняются правилам для строковых литералов в отношении escape-символов и сцепления. Они чувствительны к регистру и не могут содержать запятую, знак равенства, кавычки или символ **null** .

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

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
