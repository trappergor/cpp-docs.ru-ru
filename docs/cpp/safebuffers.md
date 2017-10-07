---
title: "safebuffers | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- safebuffers_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword (C++), safebuffers
- safebuffers __declspec keyword
ms.assetid: 0b0dce14-4523-44d2-8070-5dd0fdabc618
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ceb7d5796002bd54055b74d56a136706890494c4
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="safebuffers"></a>safebuffers
**Блок, относящийся только к системам Майкрософт**  
  
 Указывает компилятору не вставлять проверки безопасности на переполнение буфера для функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__declspec( safebuffers )  
```  
  
## <a name="remarks"></a>Примечания  
 **/GS** параметр компилятора предписывает компилятору проверять на переполнение буфера путем вставки проверок безопасности в стеке. Типы структур данных, подходящие для проверок безопасности описаны в [/GS (проверка безопасности буфера)](../build/reference/gs-buffer-security-check.md). Дополнительные сведения об обнаружении переполнения буфера см. в разделе [компилятора безопасности проверяет в глубину](http://go.microsoft.com/fwlink/?linkid=7260) на сайте MSDN.  
  
 Экспертная проверка кода вручную или внешний анализ могут показать, что функция безопасна с точки зрения переполнения буфера. В этом случае можно отключить проверки безопасности для функции, применив `__declspec(safebuffers)` ключевое слово для объявления функции.  
  
> [!CAUTION]
>  Проверки безопасности буфера — это важное средство обеспечения безопасности, которое практически не сказывается производительности. Поэтому отключать их не рекомендуется, кроме тех редких случаев, когда производительность функции исключительно важна, а сама функция заведомо безопасна.  
  
## <a name="inline-functions"></a>Встраиваемые функции  
 Объект *основной функцией* можно использовать [встраивание](inline-functions-cpp.md) ключевое слово, чтобы вставить копию *дополнительной функции*. Если `__declspec(safebuffers)` функции применяется ключевое слово, обнаружение переполнения буфера подавляется для этой функции. Тем не менее встраивание, влияет на `__declspec(safebuffers)` ключевое слово одним из следующих способов.  
  
 Предположим, что **/GS** указан параметр компилятора для обеих функций, но в основной функции `__declspec(safebuffers)` ключевое слово. Структуры данных в дополнительной функции делают ее законным объектом для проверок безопасности, поэтому такие проверки в ней не отключаются. В этом случае:  
  
-   Укажите [__forceinline](inline-functions-cpp.md) ключевое слово для дополнительной функции компилятор подставил эту функцию невзирая на оптимизации компилятора.  
  
-   Поскольку дополнительной функции является доступным для выполнения проверок безопасности, проверок безопасности также применяются к основной функцией, несмотря на то, что он указывает `__declspec(safebuffers)` ключевое слово.  
  
## <a name="example"></a>Пример  
 Следующий код показывает, как использовать `__declspec(safebuffers)` ключевое слово.  
  
```  
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
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [встроенные, __inline, \__forceinline](inline-functions-cpp.md)   
 [strict_gs_check](../preprocessor/strict-gs-check.md)
