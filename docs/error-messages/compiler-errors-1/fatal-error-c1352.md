---
title: Неустранимая ошибка C1352
ms.date: 11/04/2016
f1_keywords:
- C1352
helpviewer_keywords:
- C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
ms.openlocfilehash: fbba87cea05d666d6dc3a385ca1fe52e143fdb5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648686"
---
# <a name="fatal-error-c1352"></a>Неустранимая ошибка C1352

Недопустимый или поврежденный блок MSIL в функции "функция" из модуля "файл"

Компилятору передан файл NETMODULE, но компилятор обнаружил поврежденный элемент файла.  Для получения сведений обратитесь к создателю файла NETMODULE.

Компилятор выполняет проверку наличия не всех типов повреждений в файлах NETMODULE.  Однако он проверяет все пути выполнения в функции на наличие оператора return.

Дополнительные сведения см. в разделе [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).