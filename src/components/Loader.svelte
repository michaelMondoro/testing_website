
<div class="spinner">
    <div class="dot"></div>
    <div class="dot"></div>
    <div class="dot"></div>
    <div class="dot"></div>
    <div class="dot"></div>
</div>

<style>
/* From Uiverse.io by Mike11jr */ 
.spinner {
 width: 60px;
 height: 60px;
 position: relative;
}

.spinner .dot {
 position: absolute;
 inset: 0;
 display: flex;
 justify-content: center;
}

.spinner .dot::after {
 content: "";
 width: 7px;
 height: 7px;
 border-radius: 50%;
 background-color: var(--secondary-color);
}

@keyframes spin {
 to {
  transform: rotate(360deg);
 }
}

.spinner .dot {
 animation: spin 2s infinite;
}

.spinner .dot:nth-child(2) {
 animation-delay: 100ms;
}

.spinner .dot:nth-child(3) {
 animation-delay: 200ms;
}

.spinner .dot:nth-child(4) {
 animation-delay: 300ms;
}

.spinner .dot:nth-child(5) {
 animation-delay: 400ms;
}
</style>