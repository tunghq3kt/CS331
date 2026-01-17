# Hệ thống Hỗ trợ Trầm cảm & Lo âu bằng RAG  
**Mental Health Support Chatbot using Retrieval-Augmented Generation**

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)
[![LangChain](https://img.shields.io/badge/LangChain-0.1+-orange)](https://python.langchain.com/)
[![Groq](https://img.shields.io/badge/Groq-Llama%203.1%2070B-green)](https://groq.com/)
[![Chroma](https://img.shields.io/badge/VectorDB-Chroma-purple)](https://www.trychroma.com/)
[![Gradio](https://img.shields.io/badge/UI-Gradio-brightgreen)](https://www.gradio.app/)

## Giới thiệu

Đây là dự án đồ án môn học tại **Trường Đại học Công nghệ Thông tin – ĐHQG-HCM**, xây dựng một **chatbot hỗ trợ sức khỏe tâm thần** tập trung vào **trầm cảm** và **lo âu**, sử dụng kỹ thuật **Retrieval-Augmented Generation (RAG)**.

Mục tiêu chính:
- Cung cấp thông tin dựa trên tài liệu y khoa đáng tin cậy (PHQ-9, GAD-7, hướng dẫn điều trị)
- Giảm thiểu hallucination của LLM bằng cách neo câu trả lời vào ngữ cảnh thực tế
- Đảm bảo tính minh bạch (có thể truy vết nguồn)
- Có khả năng chạy offline / cục bộ để bảo vệ dữ liệu nhạy cảm
- Giao diện thân thiện qua Gradio

## Tính năng chính

- Tải và xử lý tài liệu PDF y khoa (DirectoryLoader + PyPDFLoader)
- Chia nhỏ văn bản thông minh (chunk 500 ký tự, overlap 50)
- Nhúng vector bằng mô hình `all-MiniLM-L6-v2` (Sentence-Transformers)
- Lưu trữ và truy xuất ngữ nghĩa với **Chroma** vector database
- Sử dụng **Llama-3.1-70B** (qua Groq API) để sinh phản hồi đồng cảm
- Giao diện chat web đơn giản, đẹp mắt bằng **Gradio**
- Hoàn toàn có thể chạy offline sau khi tạo vector store lần đầu

## Yêu cầu hệ thống

- Python 3.10+
- GPU (khuyến nghị) hoặc CPU mạnh (chạy chậm hơn)
- RAM ≥ 8GB (tốt nhất ≥ 16GB khi nhúng nhiều tài liệu)
- Kết nối Internet lần đầu để tải mô hình embedding & gọi Groq API

## Cài đặt

### 1. Clone repository

```bash
git clone https://github.com/tunghq3kt/CS331.git

