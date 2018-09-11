---
title: Проект сборки предупреждение при PRJ0042 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0042
dev_langs:
- C++
helpviewer_keywords:
- PRJ0042
ms.assetid: 682c9999-6f85-409f-b102-00c93243f74f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 260da8ac336c640ea875610b2c62e6c42c7d335e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211354"
---
# <a name="project-build-warning-prj0042"></a>Предупреждение при построении проекта PRJ0042

> «Свойство Outputs для настраиваемого этапа сборки для файла»*файл*"не задано. Настраиваемый этап сборки будет пропущен.

Настраиваемый этап построения не был выполнен, так как выходные данные не был указан.

Чтобы устранить эту ошибку, выполните одно из следующих:

- Исключите настраиваемый этап сборки из сборки.

- Добавление выходных данных.

- Удалите содержимое команды этапа настраиваемого построения.