---
title: Пути поиска в правилах
ms.date: 11/04/2016
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
ms.openlocfilehash: 26b02fa76920f0d0ff380dacd5aa76cfe8e92c79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649973"
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