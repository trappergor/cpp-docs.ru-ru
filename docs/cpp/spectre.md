---
title: spectre
ms.date: 1/23/2018
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
ms.openlocfilehash: 2377a3c23be1e27bfe4f2df23eb00823635fa05d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267262"
---
# <a name="spectre"></a>spectre

**Блок, относящийся только к системам Microsoft**

Указывает компилятору не вставки инструкций барьера упреждающего исполнения первого варианта Spectre для функции.

## <a name="syntax"></a>Синтаксис

> **__declspec (spectre(nomitigation))**

## <a name="remarks"></a>Примечания

[/Qspectre](../build/reference/qspectre.md) компилятора предписывает компилятору для вставки инструкций барьера упреждающего исполнения, где анализ показывает, что существует уязвимость системы безопасности первого варианта Spectre. Инструкции выдачи зависят от процессора. Хотя эти инструкции должны иметь минимальное влияние на производительность или размер кода, могут быть случаи, где в коде не подвержены уязвимости, а требуется максимальная производительность.

Экспертный анализ может определить, что функция безопасна с дефекта обход проверки границы первого варианта Spectre. В этом случае можно подавить формирование кода по устранению рисков внутри функции, применив `__declspec(spectre(nomitigation))` к объявлению функции.

> [!CAUTION]
> **/Qspectre** упреждающего исполнения барьера инструкции обеспечивают защиту важный элемент обеспечения безопасности и оказывает незначительное влияние на производительность. Поэтому отключать их не рекомендуется, кроме тех редких случаев, когда производительность функции исключительно важна, а сама функция заведомо безопасна.

## <a name="example"></a>Пример

В приведенном ниже коде показано использование `__declspec(spectre(nomitigation))`.

```cpp
// compile with: /c /Qspectre
static __declspec(spectre(nomitigation))
int noSpectreIssues() {
    // No Spectre variant 1 vulnerability here
    // ...
    return 0;
}

int main() {
    noSpectreIssues();
    return 0;
}
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[/Qspectre](../build/reference/qspectre.md)
