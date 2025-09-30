<template>
    <div>
  <main class="card" role="main">
    <h1>Registrar producto</h1>
    <p class="lead">Introduce los datos del producto. Campos obligatorios marcados con <strong>*</strong>.</p>

    <form id="productForm" novalidate>
      <div class="field">
        <label for="name">Nombre *</label>
        <input id="name" name="name" type="text" placeholder="Ej. Teclado inalámbrico" required minlength="2" maxlength="100" />
        <div class="err" id="err-name">El nombre es obligatorio (mín. 2 caracteres).</div>
      </div>

      <div class="row" aria-hidden="false">
        <div class="field">
          <label for="price">Precio (USD) *</label>
          <input id="price" name="price" type="number" placeholder="Ej. 25.50" step="0.01" min="0" required />
          <div class="err" id="err-price">El precio debe ser un número positivo.</div>
        </div>

        <div class="field">
          <label for="quantity">Cantidad *</label>
          <input id="quantity" name="quantity" type="number" placeholder="Ej. 10" step="1" min="0" required />
          <div class="err" id="err-quantity">La cantidad debe ser un entero >= 0.</div>
        </div>
      </div>

      <small class="hint">Se validará en el cliente antes de enviar.</small>

      <div class="actions">
        <button type="submit">Registrar</button>
        <button type="button" class="secondary" id="resetBtn">Limpiar</button>
      </div>

      <div class="success" id="successBox" role="status" aria-live="polite"></div>
    </form>
  </main>


    </div>
</template>

<script>

</script>

<style scoped>
    :root{
      --bg:#f9fafb;
      --card:#ffffff;
      --muted:#6b7280;
      --accent:#2563eb;
      --err:#dc2626;
    }
    body{
      margin:0;
      background:var(--bg);
      display:flex;
      align-items:center;
      justify-content:center;
      min-height:100vh;
      padding:24px;
    }
    .card{
      background:var(--card);
      border-radius:12px;
      box-shadow:0 6px 18px rgba(15,23,42,0.08);
      width:100%;
      max-width:520px;
      padding:20px;
    }
    h1{ margin:0 0 8px; font-size:1.25rem; }
    p.lead{ margin:0 0 18px; color:var(--muted); font-size:0.95rem; }
    .field{ margin-bottom:14px; }
    label{ display:block; font-weight:600; margin-bottom:6px; font-size:0.95rem; }
    input[type="text"],
    input[type="number"]{
      width:100%;
      padding:10px 12px;
      border:1px solid #e6e9ee;
      border-radius:8px;
      font-size:0.95rem;
      box-sizing:border-box;
    }
    input:focus{ outline:2px solid rgba(37,99,235,0.12); border-color:var(--accent); }
    .row{ display:flex; gap:12px; }
    .row .field{ flex:1; margin-bottom:0; }
    .err{ color:var(--err); font-size:0.88rem; margin-top:6px; display:none; }
    .actions{ margin-top:18px; display:flex; gap:10px; align-items:center; }
    button{
      background:var(--accent);
      color:white;
      border:0;
      padding:10px 14px;
      border-radius:8px;
      cursor:pointer;
      font-weight:600;
    }
    button.secondary{
      background:transparent;
      color:var(--muted);
      border:1px solid #e6e9ee;
    }
    .success{
      background:#ecfdf5;
      color:#065f46;
      border:1px solid #bbf7d0;
      padding:10px 12px;
      border-radius:8px;
      display:none;
      margin-top:12px;
    }
    small.hint{ display:block; color:var(--muted); margin-top:6px; font-size:0.85rem; }

</style>