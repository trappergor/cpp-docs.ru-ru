---
title: "spectre | Документы Microsoft"
ms.custom: 
ms.date: 1/23/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- spectre_cpp
- spectre
- nomitigation
dev_langs: C++
helpviewer_keywords:
- __declspec keyword (C++), spectre
- spectre __declspec keyword
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b515d25d4818cf8b6213a37f3fe78df4f3882a69
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="spectre"></a>spectre

**Блок, относящийся только к системам Microsoft**

Указывает компилятору не вставлять Spectre variant 1 наблюдающей выполнения инструкций барьера для функции.

## <a name="syntax"></a>Синтаксис

> **__declspec (spectre(nomitigation))**  

## <a name="remarks"></a>Примечания

[/Qspectre](../build/reference/qspectre.md) параметр компилятора указывает компилятору на необходимость вставки наблюдающей выполнения инструкций барьера, где анализ показывает, что Spectre variant 1 уязвимость. Конкретные инструкции выдачи зависят от процессора. Хотя эти инструкции должны иметь оказывают минимальное влияние на производительность или размер кода, может иметь случаев, когда ваш код не подвержены уязвимости и требуется максимальная производительность.

Эксперт анализа может определить, что функция безопасна с дефекта обхода проверки Spectre variant 1 границы. В этом случае можно отключить создание уменьшение кода внутри функции путем применения `__declspec(spectre(nomitigation))` к объявлению функции.

> [!CAUTION]
> **/Qspectre** наблюдающей выполнения инструкций барьера обеспечивают защиту важных безопасности и иметь практически не сказывается на производительности. Поэтому отключать их не рекомендуется, кроме тех редких случаев, когда производительность функции исключительно важна, а сама функция заведомо безопасна.

## <a name="example"></a>Пример

Следующий код показывает, как использовать `__declspec(spectre(nomitigation))`.

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

[__declspec](../cpp/declspec.md)  
[Ключевые слова](../cpp/keywords-cpp.md)  
[/Qspectre](../build/reference/qspectre.md)  
