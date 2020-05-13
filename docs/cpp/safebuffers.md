---
title: safebuffers
ms.date: 11/04/2016
f1_keywords:
- safebuffers_cpp
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
ms.openlocfilehash: bc4736ce233ce026ecab9ef38ac8379466b5a0bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365583"
---
# <a name="safebuffers"></a>safebuffers

**Microsoft Специфический**

Указывает компилятору не вставлять проверки безопасности на переполнение буфера для функции.

## <a name="syntax"></a>Синтаксис

```
__declspec( safebuffers )
```

## <a name="remarks"></a>Remarks

Опция компилятора **/GS** заставляет компилятор тестировать перерасход буфера, вставляя проверки безопасности в стек. Типы структур данных, которые имеют право на проверку безопасности, описаны в [/GS (Buffer Security Check)](../build/reference/gs-buffer-security-check.md). Для получения дополнительной информации об обнаружении буфера перехиран, [см.](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)

Экспертная проверка кода вручную или внешний анализ могут показать, что функция безопасна с точки зрения переполнения буфера. В этом случае можно пресекать проверки безопасности функции, применяя ключевое слово **__declspec (safebuffers)** к декларации функций.

> [!CAUTION]
> Проверки безопасности буфера — это важное средство обеспечения безопасности, которое практически не сказывается производительности. Поэтому отключать их не рекомендуется, кроме тех редких случаев, когда производительность функции исключительно важна, а сама функция заведомо безопасна.

## <a name="inline-functions"></a>Встраиваемые функции

*Основная функция* может использовать [подчеркивая](inline-functions-cpp.md) ключевое слово, чтобы вставить копию *вторичной функции.* Если ключевое слово **__declspec (safebuffers)** применяется к функции, обнаружение перезапуска буфера подавляется для этой функции. Тем не менее, приведение влияет на **__declspec (safebuffers)** ключевое слово следующим образом.

Предположим, что для обеих функций указан параметр компилятора **/GS,** но основная функция определяет ключевое слово **__declspec (safebuffers).** Структуры данных в дополнительной функции делают ее законным объектом для проверок безопасности, поэтому такие проверки в ней не отключаются. В данном случае:

- Укажите [__forceinline](inline-functions-cpp.md) ключевое слово на вторичной функции, чтобы заставить компилятор ввести эту функцию независимо от оптимизации компилятора.

- Поскольку второстепенная функция имеет право на проверку безопасности, проверки безопасности также применяются к основной функции, даже если она указывает ключевое слово **__declspec (safebuffers).**

## <a name="example"></a>Пример

В следующем коде показано, как использовать ключевое слово **__declspec (safebuffers).**

```cpp
// compile with: /c /GS
typedef struct {
    int x[20];
} BUFFER;
static int checkBuffers() {
    BUFFER cb;
    // Use the buffer...
    return 0;
};
static __declspec(safebuffers)
    int noCheckBuffers() {
    BUFFER ncb;
    // Use the buffer...
    return 0;
}
int wmain() {
    checkBuffers();
    noCheckBuffers();
    return 0;
}
```

**END Microsoft Специфический**

## <a name="see-also"></a>См. также раздел

[__declspec](../cpp/declspec.md)<br/>
[Keywords](../cpp/keywords-cpp.md)<br/>
[вон, __inline, \__forceinline](inline-functions-cpp.md)<br/>
[strict_gs_check](../preprocessor/strict-gs-check.md)
