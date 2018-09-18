---
title: Сопоставления констант и глобальных переменных | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _tenviron
- _TEOF
- _tfinddata_t
dev_langs:
- C++
helpviewer_keywords:
- tfinddatat function
- tenviron function
- TEOF type
- _TEOF type
- generic-text mappings
- _tenviron function
- _tfinddata_t function
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94cee77f82f850560cc5fe50e13b85c58b7187ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077857"
---
# <a name="constant-and-global-variable-mappings"></a>Сопоставления констант и глобальных переменных

Сопоставления универсальных текстовых констант, глобальных переменных и стандартных типов определяются в TCHAR.H и зависят от того, определена ли в вашей программе константа `_UNICODE` или `_MBCS`.

### <a name="generic-text-constant-and-global-variable-mappings"></a>Сопоставления универсальных текстовых констант и глобальных переменных

|Универсальный текст - имя объекта|Однобайтовая кодировка (_UNICODE, _MBCS не определены)|_MBCS определено|_UNICODE определено|
|----------------------------------|--------------------------------------------|--------------------|-----------------------|
|`_TEOF`|`EOF`|`EOF`|`WEOF`|
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|

## <a name="see-also"></a>См. также

[Универсальные текстовые сопоставления](../c-runtime-library/generic-text-mappings.md)<br/>
[Сопоставления типов данных](../c-runtime-library/data-type-mappings.md)<br/>
[Сопоставления подпрограмм](../c-runtime-library/routine-mappings.md)<br/>
[Пример программы с использованием универсального текста](../c-runtime-library/a-sample-generic-text-program.md)<br/>
[Использование универсальных текстовых сопоставлений](../c-runtime-library/using-generic-text-mappings.md)