# DoLuong_PSNR
B1:sau khi tai file source code ve giai nen thu muc.
B2:cd src/.
B3:sua trong file stats.cpp.
Tim den doan .
namespace stats {
	static double compute_psnr(const unsigned char *ref, const unsigned char *cmp, const unsigned int& sz) {
		double mse = 0.0;
		for(unsigned int i = 0; i < sz; ++i) {
			const int	diff = ref[i]-cmp[i];
			mse += (diff*diff);
		}
		mse /= (double)sz;
		if (0.0 == mse) mse = 1e-10;
	//////sua cai nay	return 100.0*log10(65025.0/mse);
		return 3.0*log10(65025.0/mse);
	}
B4:make.
B5:su dung cau lenh.
	qpsnr -r SEND.h264 RECEIVE.h264
thu vao file text, duoc chi so PSNR.
