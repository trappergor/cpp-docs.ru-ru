---
title: '&lt;see&gt; (Visual C++) | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <see>
- see
dev_langs:
- C++
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 909177f7b3b475bd049ca311fc3c12c840422cde
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401203"
---
# <a name="ltseegt-visual-c"></a>&lt;see&gt; (Visual C++)

Тег \<see> позволяет задать ссылку из текста. Используйте тег [\<seealso>](../ide/seealso-visual-cpp.md)?/ чтобы указать текст, который должен отображаться в разделе "См. также".

## <a name="syntax"></a>Синтаксис

```
<see cref="member"/>
```

#### <a name="parameters"></a>Параметры

*member*<br/>
Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.  Заключите имя в одинарные или двойные кавычки.

Компилятор проверяет, существует ли элемент кода, и разрешает `member` в имя элемента в выходных XML-данных.  Если компилятору не удается найти `member`, он выдает предупреждение.

## <a name="remarks"></a>Примечания

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).

В разделе [\<summary>](../ide/summary-visual-cpp.md) можно найти пример использования тега \<see>.

Компилятор Visual C++ будет пытаться разрешить ссылки cref за один проход по комментариям документации.  Поэтому если при использовании правил поиска C++ компилятор не найдет символ, ссылка будет помечена как не разрешенная. Дополнительные сведения см. в описании [\<seealso>](../ide/seealso-visual-cpp.md).

## <a name="example"></a>Пример

Следующий пример показывает, как можно создать ссылку cref на универсальный тип, чтобы компилятор разрешил ее.

```
// xml_see_cref_example.cpp
// compile with: /LD /clr /doc
// the following cref shows how to specify the reference, such that,
// the compiler will resolve the reference
/// <see cref="C{T}">
/// </see>
ref class A {};

// the following cref shows another way to specify the reference,
// such that, the compiler will resolve the reference
/// <see cref="C < T >"/>

// the following cref shows how to hard-code the reference
/// <see cref="T:C`1">
/// </see>
ref class B {};

/// <see cref="A">
/// </see>
/// <typeparam name="T"></typeparam>
generic<class T>
ref class C {};
```

## <a name="see-also"></a>См. также

[Документация XML](../ide/xml-documentation-visual-cpp.md)