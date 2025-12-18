# Test REST API

GitHub Pages + Supabase REST API を用いた CRUD サンプル

## Overview
このプロジェクトは、React と Supabase を利用した REST API 連携の Todo アプリケーションです。

フロントエンドは GitHub Pages に静的サイトとしてデプロイされており、
バックエンド（データベースおよび REST API）は Supabase が提供しています。
独自のバックエンドサーバーを構築することなく、フロントエンドから直接 REST API を利用して CRUD 操作を行う構成を採用しています。

本アプリでは、以下の点を重視しています。
- REST API を通じた Todo の取得・追加・更新・削除（CRUD）
- フロントエンドとバックエンドの責務分離
- 環境変数および Row Level Security（RLS）を用いた安全な API 利用
- 小規模なプロダクトやプロトタイプに適した、現実的なアーキテクチャ

REST API 連携の学習用途としても、
実際に公開可能なサンプルアプリとしても使える構成になっています。


## Tech Choices

フロントエンド

# React（Create React App）
コンポーネント指向で UI を構築し、シングルページアプリケーション（SPA）として実装しています。
# React Router
Todo 一覧、詳細表示、新規作成などの画面遷移をクライアントサイドで管理しています。
# Axios
Supabase が提供する REST API との通信を行うための HTTP クライアントとして使用しています。
# GitHub Pages
フロントエンドを静的サイトとしてホスティングしています。
無料で運用でき、フロントエンドとバックエンドを明確に分離できる点を重視しました。

バックエンド / API

# Supabase（PostgreSQL + REST API）
Supabase により、以下を利用しています。
- マネージド PostgreSQL データベース
- 自動生成される REST API（PostgREST）
- ブラウザから安全にアクセスするための Row Level Security（RLS）
これにより、独自サーバーを構築・運用することなく、
永続的なデータを扱えるバックエンドを実現しています。

# Row Level Security（RLS）
ブラウザに公開される API キー（anon key）を使用する前提で、
データの取得・追加・更新・削除を制御しています。
クライアントサイドから直接 API を呼び出しても安全性を保てる点が特徴です。


## この構成を選んだ理由

フロントエンドを シンプルかつ低コストで公開できる。
バックエンドサーバーの構築・運用が不要。
モックではなく実際のデータベースと REST API を利用できる。
小規模アプリやプロトタイプで実務でも使われる構成である。
