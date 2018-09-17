---
title: Пути поиска в правилах | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c96ee89367c3ac289dffde9029cb2b5d3cdc3e89
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703980"
---
# <a name="search-paths-in-rules"></a>Пути поиска в правилах

```
{frompath}.fromext{topath}.toext:
   commands
```

## <a name="remarks"></a>Примечания

Правило вывода применимо к зависимости только в том случае, если пути, указанные в зависимости, точно соответствует путям правила вывода. Укажите каталог зависимого объекта, в *frompath* и целевого объекта каталога в *параметре topath*; пробелы не допускаются. Укажите только один путь для каждого расширения. Путь на одно расширение требуется указать путь на другой. Чтобы указать текущего каталога, используйте точку (.) или пустых фигурных скобок ({}). Макросы могут представлять *frompath* и *параметре topath*; они вызываются во время предварительной обработки.

## <a name="example"></a>Пример

### <a name="code"></a>Код

```
{dbi\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUDBI) $<

{ilstore\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{misc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{misc\}.c{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{msf\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{bsc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{mre\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{namesrvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{src\cvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<
```

## <a name="see-also"></a>См. также

[Определение правила](../build/defining-a-rule.md)