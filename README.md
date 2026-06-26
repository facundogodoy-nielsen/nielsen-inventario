# Nielsen Inventario — Despliegue en Vercel

Sistema de control de inventario para Nielsen Logística y Expediciones S.A.

## Desplegar en Vercel
1. Entrá a https://vercel.com
2. Add New → Project
3. Arrastrá el contenido de este ZIP (index.html, vercel.json, README.md)
4. Deploy

## Tabla Supabase (sincronización en la nube)
En el SQL Editor de Supabase ejecutá:

```sql
create table if not exists inventario (
  id text primary key,
  data jsonb,
  updated_at timestamptz default now()
);
alter table inventario enable row level security;
create policy "allow all" on inventario for all using (true) with check (true);
```

## Acceso
- Modo Lector (por defecto): solo consulta
- Modo Editor: PIN 1979
