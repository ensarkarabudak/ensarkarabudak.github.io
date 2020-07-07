---
layout: post
title: "Öyler Yolu ve Devresi(Euler Path and Circuit)"
---

Bir G grafındaki tüm ayrıtları içeren bir yol varsa buna “**Euler Path(Öyler Yolu)**” denir.
Bir G grafında başlagıç ayrıtından başlayıp tüm ayrıtları kapsayan bir devre varsa buna “**Euler Circuit(Öyler Yolu)**” denir.
Burada önemli olan nokta ayrıtlar üzerinden **yalnızca** 1 kere geçilmelidir.

> Teorem:En az iki düğümlü bir grafta tüm düğümlerin derecesi çift ise bu grafta öyler devresi(euler circuit) vardır.

> Teorem:En az iki düğümlü bir grafta sadece 2 adet düğümün derecesi çift ise öyler yolu(euler path) vardır.

![image-center]({{ '/images/oyler-yolu-ve-devresi-euler-path-and-circuit.png' | absolute_url }}){: .align-center}


#### Öyler devresi(Euler circuit) pseudo kodu(code)

```pseudocode
procedure Euler(G: connected multigraph with all vertices of
even degree)
circuit := a circuit in G beginning at an arbitrarily chosen
vertex with edges successively added to form a path that
returns to this vertex
H := G with the edges of this circuit removed
while H has edges
begin
subcircuit := a circuit in H beginning at a vertex in H that
also is an endpoint of an edge of circuit
H : = H with edges of subcircuit and all isolated vertices
removed
circuit : = circuit with subcircuit inserted at the appropriate
vertex
end {circuit is an Euler circuit}


```