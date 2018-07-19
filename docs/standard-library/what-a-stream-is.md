---
title: Что такое поток | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], iostream programming
- data [C++], reading
- streams [C++], in iostream classes
- streams [C++]
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47f56a3d717c2dc9cebb3df30739954e5f6bf9e1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853743"
---
# <a name="what-a-stream-is"></a>Что такое поток

Как и C, в C++ нет встроенных потоков ввода-вывода. Однако в состав всех компиляторов C++ входит системный объектно ориентированный пакет ввода-вывода — классы iostream. Центральной концепцией классов iostream является поток. Можно считать, что поток — это смарт-файл, который выступает в качестве источника и назначения для байт. Характеристики потока определяется его классом и пользовательскими операторами вставки и извлечения.

С помощью драйверов устройств дисковая операционная система взаимодействует с клавиатурой, монитором, принтером и портами ввода-вывода как с расширенными файлами. Классы iostream взаимодействуют с этими расширенными файлами. Встроенные классы поддерживают чтение из памяти и запись в память, причем синтаксис этих операций идентичен синтаксису для операций дискового ввода-вывода, что позволяет легко создавать производные классы потока.

## <a name="in-this-section"></a>В этом разделе

[Альтернативные варианты ввода-вывода](../standard-library/input-output-alternatives.md)

## <a name="see-also"></a>См. также

[Программирование iostream](../standard-library/iostream-programming.md)<br/>
