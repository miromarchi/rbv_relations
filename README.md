rbv_relation
============

Retebuonvivere: relation

Description
-----------
This is a [drupal feature][2]. It uses mainly [relation module][3] and [rules module][4] (plus [rules_conditional][5]) to automatically generate simmetrical relations (cooperations between [organizations][6] of the civil society).

Organization members (users) create [collaborations][7] from their organization to [projects][8]. On the basis of these collaborations, relations are autogenerated. In network theory (in Social Network Analysis for instance) the procedure of generating a network of collaborators on the basis of copartecipation on projects (or events in other cases) is called projection or transformation of a bipartite (or 2mode) network onto a monopartite (or 1-mode) network. Network analysis software do this by means of matrix multiplication, but in drupal we managed to implement this funcionality in a different way. 

We update 1-mode relations every time a 2-mode relation (collaborations to projects) are updated. We do it by means of rules module and relation module. 

* E.g. Organization1 creates a collaboration to project2 of Organization2: 

```
    Org1 → Project2
```

* The rule is fired: get all collaborators at project2 (let's say they are Organization2, Organization1 and Organization3). 

```
Org1 \
Org2 -|→ Project2
Org3 /
```

* Now creates (if not present) a 1-mode relation between Organization1 and Organization2, Organizatio3 and Organization2, Organization1 and Organization3.

```
Org1 ←→ Org2
Org2 ←→ Org3
Org1 ←→ Org3
```

Submodule of
------------
This repository is a submodule of [retebuonvivere][0].

Wiki
----
Go to the [relation wiki][1] for more stuff about how we want to implement relations in this project.

[0]: https://github.com/fonzy85vr/retebuonvivere.
[1]: https://github.com/miromarchi/rbv_relation/wiki
[2]: https://drupal.org/project/features
[3]: https://drupal.org/project/relation
[4]: https://drupal.org/project/rules
[5]: https://drupal.org/project/rules_conditional
[6]: https://github.com/miromarchi/rbv_org
[7]: https://github.com/miromarchi/rbv_relorg
