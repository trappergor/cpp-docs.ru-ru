---
title: Общие сведения о токенах
ms.date: 11/04/2016
ms.assetid: 2978cbf6-e66e-46fc-9938-caa052f2ccf7
ms.openlocfilehash: 4fdc1cf4c4e5a89cc9ecf029e64b6eb5422cd6a3
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56149119"
---
# <a name="summary-of-tokens"></a>Общие сведения о токенах

*token*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*keyword*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*string-literal*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*operator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*punctuator*

*preprocessing-token*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*header-name*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pp-number*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*character-constant*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*string-literal*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*operator punctuator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;любой символ, отличный от пробела, который не может быть одним и перечисленных выше элементов

*header-name*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**\<** *path-spec* **>**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**"** *path spec* **"**

*path-spec*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Допустимый путь к файлу

*pp-number*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**.** *digit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pp-number* *digit* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pp-number* *nondigit*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pp-number*  **e**  *sign*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pp-number* **E** *sign*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pp-number* **.**

## <a name="see-also"></a>См. также

[Лексическая грамматика](../c-language/lexical-grammar.md)
