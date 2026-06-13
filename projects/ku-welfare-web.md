# KU Welfare Web — Rental & Printing Portal

> Jan 2026 – Present · **Frontend** · Team of 2 · Live in production
> [Live](https://ku-welfare-web.vercel.app/) · [Repository](https://github.com/41-Welfare-Web/KU_WelfareWeb_FrontEnd)

## Overview

The official web portal of Konkuk University's 41st Student Welfare Committee. It digitalizes campus welfare operations — item rental and printing services — that were previously handled manually, drastically reducing administrative overhead. Currently **live and serving students**.

## Architecture

```mermaid
flowchart LR
    A[React + Vite SPA] --> B[React Router]
    A --> C[Axios API client]
    C --> D[Welfare backend]
    A --> E[Vercel deploy]
```

A React 19 + Vite single-page app, styled with TailwindCSS 4, talking to the welfare backend through an Axios client, deployed on Vercel.

## My role

Frontend architecture, implementation, and Vercel deployment (2-person team).

## Tech stack

`React` · `TypeScript` · `Vite` · `TailwindCSS` · `React Router` · `Axios` · `Vercel`
